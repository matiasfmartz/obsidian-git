# Credenciales APIM

## GPAG

### Desarrollo | DEV | DESA

Application ID f0b06c45
Application key 6e58a62377b8d6abbd6486fbbecd48ca


### Integración | INT | INTE

Application ID b10050f3
Application key d2ee179276018f36546014ea08b42698


### Homologación | QAS | HOMO

Application ID f66a0f6c
Application key 25d00320c1db990644fca28063343562


### Producción | PRD | PROD

Application ID fd270966
Application key 69429ec4f5a8d31c2398ad2f66e6cd4a


---

## PPAG

### Desarrollo | DEV | DESA

Application ID 43f1569d
Application key 9b581b871bed5b7833cbee5ae1b8aaac


### Integración | INT | INTE

Application ID c72d7bef
Application key 3c28922e5914a19b4468ec3dff13edbe


### Homologación | QAS | HOMO

Application ID c6391711
Application key d930d48d53e0840f1075d639607ed857


### Producción | PRD | PROD

Application ID 549f0d12
Application key ba8ef6250828691338211b82fa46b86b


---

# URLs OCP4

- **Dev** - https://console-openshift-console.apps.paas-dev.bancogalicia.com.ar
- **Stg** - https://console-openshift-console.apps.paas-stg.bancogalicia.com.ar
- **Qas** - https://console-openshift-console.apps.paas-qas.bancogalicia.com.ar
- **Prdpg** - https://console-openshift-console.apps.paas-prdpg.bancogalicia.com.ar
- **Prdmz** - https://console-openshift-console.apps.paas-prdmz.bancogalicia.com.ar
- **DMZ** - https://console-openshift-console.apps.paas-dmz.bancogalicia.com.ar

---

# URLs ONB

## BackOffice

- **Dev** - https://dw2019iisonb01:2704/Logs/Index
- **Homo** - https://hw2019iisonb01.bancogalicia.com.ar:2704/Home/EnvironmentDashboard/1
- **Prod** - https://tw2019iisonb01:8070/Logs/Index

## RPs

- ONB RPs Release - https://release.bancogalicia.com.ar

---

# URLs Kibana
## GPAG
Dashboard Kibana GPAG - http://dkibana11.bancogalicia.com.ar:5601/s/openshift/app/discover#/?_g=(filters:!(),refreshInterval:(pause:!t,value:0),time:(from:now-15m,to:now)))&_a=(columns:!(),filters:!(),index:'7e6ea2f0-f8f4-11ea-98c2-d1283300ba47',interval:auto,query:(language:kuery,query:''),sort:!(!('@timestamp',desc)))

## PPAG
Dashboard Kibana PPAG - http://dkibana11.bancogalicia.com.ar:5601/s/openshift/app/discover#/?_g=(filters:!(),refreshInterval:(pause:!t,value:0),time:(from:now-15m,to:now)))&_a=(columns:!(),filters:!(),index:'335b2340-58c0-11ee-8279-d143d5352c0c',interval:auto,query:(language:kuery,query:''),sort:!(!('@timestamp',desc)))

## ONB

- **Desa** - http://dkibana11.bancogalicia.com.ar:5601/s/onb/app/discover#/
- **Homo** - http://dkibana11.bancogalicia.com.ar:5601/s/onb/app/discover#/)
- **Prod** - http://kibana/s/onb/app/discover#/view/2b54ad10-39ef-11ed-927a-e53a157a3202

---

# Links BO POM por Ambiente

- **Dev** - https://frontend-pobo-backoffice-dev.apps.paas-dev.bancogalicia.com.ar `^86d16a` ^99776e
- **Int** - https://frontend-pobo-backoffice-int.apps.paas-stg.bancogalicia.com.ar) `^850372` ^a990a5
- **Qas** - https://frontend-pobo-backoffice-qas.apps.paas-qas.bancogalicia.com.ar) `^b3090b` ^62cc8d
- **Prd** - https://frontend-pobo-backoffice-prd.apps.paas-prd.bancogalicia.com.ar `^4ca252` ^868c0e

---

# Otros Enlaces de Referencia

- **Tablero Galicia SAFE** - https://bancogaliciaprod.service-now.com/now/nav/ui/classic/params/target/sn_safe_%24safe_board.do#/teamSprintTracking
- **Base de conocimiento** - https://bancogaliciaprod.service-now.com/sp?id=index
- **Repositorio CNET** - https://github.bancogalicia.com.ar/cnet-crossnetcore
- **Reporte Veracode** - https://myapps.microsoft.com/signin/Veracode/d6d6fd65-7442-4be7-9c02-4125bcbbc3e9?tenantId=934de3fe-416c-4e4c-b035-32df9344eac4) ^35cb34
- **Dashboard AppDynamics** - https://bancogalicia-prod.saas.appdynamics.com/controller/#/location=APP_DASHBOARD&timeRange=last_1_hour.BEFORE_NOW.-1.-1.60&application=3764&dashboardMode=force
- **Brick SPA Starter Kit** - https://github.bancogalicia.com.ar/febg-commons/brick-spa-starter-kit ^41e9d4
- **Jenkins** - https://devopstoolkit.bancogalicia.com.ar/blue/pipelines/
- catalogo APIM - https://apim-catalogo-frontend-icta-ictransapi-prd.apps.paas-prd.bancogalicia.com.ar/apim/apis/?ENV=PRD