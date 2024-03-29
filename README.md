# SAP Commerce (Hybris) 2005 + Spartacus docker-compose script

> Easy-to-run script to run SAP Commmerce with Spatacus storefront *locally*.
> Script focuses on B2B capabilities and Powertools storefront. **Non-production use only.**

## How to run

1. Install docker and docker-compose (https://docs.docker.com/get-docker/, https://docs.docker.com/compose/install/)
2. Download SAP Commerce package (`CXCOM200500P_0-70004955.ZIP`) from SAP Product pages
3. Move `CXCOM200500P_0-70004955.ZIP` into `hybris-b2b-spartacus/hybris-b2b`. If you want to use another 
   version of SAP Commerce, then edit `hybris-b2b-spartacus/hybris-b2b/Dockerfile` and 
   replace `CXCOM200500P_0-70004955.ZIP` with your archive filename)
4. Open terminal, navigate to `hybris-b2b-spartacus` folder and run command:
    ```
        docker-compose build
    ```
5. Wait until SAP Commerce initialize (may take up to an hour)
6. Now start the containers:
    ```
        docker-compose up -d
    ```
    If you want to start only SAP Commerce server (w/o Spartacus FE), use the following command:
    ```
        docker-compose up -d hybris
    ```

7. Wait for SAP Commerce to start (may take 10 min)
8. Navigate to http://localhost:4200/ in your browser
    > In some cases you may encounter certificate issue during the first OCC calls. 
      Then just open page https://localhost:9002/occ/v2/powertools-spa/cms/pages?fields=DEFAULT&pageType=ContentPage&pageLabelOrId=homepage&lang=en&curr=USD 
      in your browser and confirm certificate exception)

## Local Links

* Spartacus Storefront - http://localhost:4200/
* Backoffice - https://localhost:9002/backoffice/ (use `admin`/`nimda` as user/password)
* Smartedit - https://localhost:9002/smartedit/ (use `admin`/`nimda` as user/password)
