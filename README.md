# Helm chart
1. CD into the helm directory
2. Rnn `helm upgrade --install nginx-app  .`
3. `nginx-app` in cmd line is just a name we can give for the app
4. The above cmd will update/create deployment

## Publishing helm into docker registry
1. CD into parent directory of helm chart dir
2. Run `helm package nginx-chart`
3. `nginx-chart` is the helm directory name
4. It will create a tar file
5. Run `helm push <tartfile> oci://registry-1.docker.io/hariramprasanth`

## Using helm chart from docker hub
1. Login into helm registry in docker hub
2. Run `helm registry login registry-1.docker.io   --username hariramprasanth`
3. Give password
4. Run `helm pull oci://registry-1.docker.io/hariramprasanth/nginx-helm-chart`
5. It will download a tar file which we published earlier
6. Use `tar zxvf <tar file>` to extract the tar. It will have the same helm directory
7. Now we can use it to install helm charts
8. Or Run `helm install nginx-app-in-eks oci://registry-1.docker.io/hariramprasanth/nginx-helm-chart` without pulling tar into local


