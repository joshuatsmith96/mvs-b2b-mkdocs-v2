# MVS B2B Toolkit VM

-----

## Overview

The MVS B2B toolkit consists of two virtual machines:

  * **Windows 10:** This is the traditional HCL Commerce Toolkit, configured with a local database (DB2) and local search (SOLR). It also has the code for HCL Commerce Tooling, Customer Service Hub, and the MVS storefront.
  * **CentOS Stream 9:** This VM runs Orchestration and Redis Docker containers. Developers generally won't do much in this VM, but it needs to run alongside the Toolkit VM for the storefront to work.

-----

## Download

You can find the VM images on Google Drive:

`[Customer] > MVS > Development > MVS B2B Toolkit VM`

Ask **Andy Bradtke**, **Ryan Vennor**, or **Baron Lam** for access.

-----

## System Users

| VM | User | Password |
| :--- | :--- | :--- |
| **Windows VM** | `admin` | `BlueSky1` (for login) |
| | `db2admin` | `passw0rd` |
| | `wcs` | `passw0rd` |
| **Linux VM** | `admin` | `BlueSky1` (for login) |
| | `root` | `BlueSky1` |

-----

## HCL Commerce Users

### Admins

  * `wcsadmin`/`passw0rd`
  * `spiuser`/`QxV7uCk6RRiwvPVaa4wdD78jaHi2za8ssjneNMdu3vgqi`

### Shoppers

Three organizations have been created for MVS clinics:

1.  **Customer Organizations** - Functions as the parent organization for all Bill-To's.
2.  **BLUESKY EMERGENCY VET SERVICE** - A sample Bill-To.
3.  **BLUESKY SATELLITE OFFICE** - A sample Ship-To.

<!-- end list -->

  * A sample user, `test.user@blueskycommerce.io`/`bluesky2`, has been created under the Ship-To.

-----

## Setup - Windows VM

### Git

If not already done, generate and/or add an SSH key to your BitBucket account.

1.  Open a command prompt and run `cd C:\Users\admin\.ssh`.
2.  Run `ssh-keygen -t rsa -b 2048`.
      * Leave the filename blank (it defaults to `id_rsa`) and set a password if you wish.
      * This generates two files in `C:\Users\admin\.ssh`: `id_rsa` and `id_rsa.pub`.
3.  Open `id_rsa.pub` and copy the contents into Bitbucket.
4.  If you already have an SSH key, copy `id_rsa` to `C:\Users\admin\.ssh`.
5.  Open Git Bash and run `git config --global user.name "FIRST_NAME LAST_NAME"` and `git config --global user.email "email@example.com"` to set your name and email.

### Orchestration

1.  With administrative rights, edit `C:\Windows\System32\drivers\etc\hosts`.
2.  Update the `orchestration` host with the **IP address of your Linux VM**. To get the IP address, open a terminal window on the Linux VM and run `ip a | grep 192`.
3.  **NOTE:** This IP may change with each restart, so this step may need to be repeated. If the IP changes while the Evolve store is running, the Evolve store and search server must be restarted.

-----

## Setup - Linux VM

### Orchestration

1.  Edit `/home/admin/HCLCommerce/HCL-Commerce-DevOps-9.1.16.1/docker-compose/env.sh`.
2.  Update `TOOLKIT_HOST_IP` with the **IP address of your Windows VM**. To get the IP, open a command prompt on the Windows VM and run `ipconfig /all`.
3.  **NOTE:** This IP may change with each restart. If the Windows IP changes and the orchestration layer was running, you must restart it by running `./teardown.sh` and then `./deploy.sh`.

-----

## Usage

| Application | Source Control | Local Path | Usage Instructions |
| :--- | :--- | :--- | :--- |
| **Windows VM** | | | |
| Backend | `https://bitbucket.org/blueskytp/mvs-b2b-backend` | `C:\WCDE_90\workspace` | Use HCL Commerce Toolkit. |
| Backend Tooling | `https://bitbucket.org/blueskytp/mvs-b2b-tooling` | `C:\GitRepos\mvs-b2b-tooling` | Open a terminal, navigate to `C:\GitRepos\mvs-b2b-tooling\commerce-tooling`, run `npm start`. Access new tooling at `https://localhost:7443/tooling` or Management Center at `https://localhost:7443/lobtools/cmc/ManagementCenter`. |
| Frontend | `https://bitbucket.org/blueskytp/mvs-b2b-frontend` | `C:\GitRepos\mvs-b2b-frontend` | Open a terminal, navigate to `C:\GitRepos\mvs-b2b-frontend`, run `yarn dev`. Access storefront at `http://localhost:3003/mvs`. |
| Customer Service Hub | `https://bitbucket.org/blueskytp/mvs-b2b-customer-service-hub` | `C:\GitRepos\mvs-b2b-customer-service-hub` | Open a terminal, navigate to `C:\GitRepos\mvs-b2b-customer-service-hub`, run `npm start`. Access Hub at `http://localhost:4000/csr`. |
| **Linux VM** | | | |
| Orchestration | | `/home/admin/HCLCommerce/HCL-Commerce-DevOps-9.1.16.1/docker-compose` | As "admin," open a terminal, run `cd /home/admin/HCLCommerce/HCL-Commerce-DevOps-9.1.16.1/docker-compose`. To start, run `./deploy.sh`. To shut down, run `./teardown.sh`. |

-----

## Installed Software

### Windows VM

  * HCL Commerce 9.1.16.0
  * WebSphere Applications Server 9.0.5.20 + PH61504 +PH61546 + PH61489 + PH61808
  * WebSphere Application Server V8.5.5 Liberty 24.0.0.6
  * IBM DB2 11.5.8

### Linux VM

  * HCL Commerce 9.1.16.1 DevOps bundle
  * Docker Engine Community 27.3.1
  * Docker Compose 2.29.7

-----

## Database

  * **JDBC Connection:** `jdbc:db2://localhost:50000/toolkit`
  * **DB Admin:** `db2admin`
  * **DB User:** `wcs`
  * **Backups:**
      * **Path:** `C:\DB_Backup`
      * **Helpful commands:** `db2 restore db toolkit` and `db2 backup db toolkit compress`
  * **Configuration:** The following command was run on the toolkit database: `db2 update db cfg using logfilsiz 4000 logprimary 100 logsecond 100`

-----

## Search

  * **Engine:** SOLR
  * **URLs:**
      * `http://localhost:3737/solr/admin/cores`
      * `http://localhost:3737/solr/MC_10001_CatalogEntry_en_US/select?q=*:*`
      * `http://localhost:3737/solr/MC_10001_CatalogGroup_en_US/select?q=*:*`
  * **Helpful commands:**
      * To build the index:
        ```bash
        curl --user spiuser:QxV7uCk6RRiwvPVaa4wdD78jaHi2za8ssjneNMdu3vgqi -k -X POST https://localhost:443/wcs/resources/admin/index/dataImport/build?masterCatalogId=10001
        ```
      * To build the purchase history sub-index:
        ```bash
        curl --user spiuser:QxV7uCk6RRiwvPVaa4wdD78jaHi2za8ssjneNMdu3vgqi -k -X POST "https://localhost:443/wcs/resources/admin/index/dataImport/build?masterCatalogId=10001&indexType=CatalogEntry&indexSubType=PurchaseHistory"
        ```
  * **Log files:** Located in `C:\WebSphere\Liberty\usr\servers\searchServer\logs`. Trace strings can be configured in `C:\WebSphere\Liberty\usr\servers\searchServer\configDropins\overrides\server.xml`.

-----

## VPN

MVS uses **WatchGuard Mobile VPN**, which is installed on the toolkits. Each user has their own set of credentials provided by MVS.

-----

## Postman

A "shared" Postman account is used on all toolkits for automated testing.

  * **Shared Account:** `ryan.vennor+shared@blueskycommerce.io`/`:6t&4xPsV9#_+uD`
  * **Collection:** "MVS Automated Tests" will be used to store test cases and is integrated with Jenkins.
  * **Reference:** `/wiki/spaces/PD/pages/3000729625`

-----

## AS400

**DBeaver** is installed and configured with a JDBC connection to the MVS AS400. Users needing to connect must request credentials from MVS.

-----

## DataLoad

The following line was added to `C:\WCDE_V9\bin\dataloadenv.bat` to fix an issue with `.jar` files not being picked up:

`set DATALOAD_CP=%DATALOAD_CP%;%WCTOOLKIT%\workspace\DataLoad\lib\*`