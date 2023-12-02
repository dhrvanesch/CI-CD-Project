
![live](https://github.com/dhrvanesch/Java-App/assets/13959713/a994e3ef-6485-469c-aee4-7391a304926b)








~~~~
[ansadmin@ansible-server docker]$ ansible-playbook -i /opt/docker/hosts/ create-docker-image.yml

PLAY [ansible] *****************************************************************************************************************************************************************************************

TASK [Gathering Facts] *********************************************************************************************************************************************************************************
[WARNING]: Platform linux on host 172.31.23.97 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could change this. See
https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information.
ok: [172.31.23.97]

TASK [create docker image] *****************************************************************************************************************************************************************************
changed: [172.31.23.97]

TASK [create tag] **************************************************************************************************************************************************************************************
changed: [172.31.23.97]

TASK [push docker image] *******************************************************************************************************************************************************************************
changed: [172.31.23.97]

PLAY RECAP *********************************************************************************************************************************************************************************************
172.31.23.97               : ok=4    changed=3    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
~~~~


~~~~

[ansadmin@ansible-server docker]$ ansible-playbook -i /opt/docker/hosts/ kubernetes-deploy.yml

PLAY [kubernetes] **************************************************************************************************************************************************************************************

TASK [Gathering Facts] *********************************************************************************************************************************************************************************
[WARNING]: Platform linux on host 172.31.27.222 is using the discovered Python interpreter at /usr/bin/python, but future installation of another Python interpreter could change this. See
https://docs.ansible.com/ansible/2.9/reference_appendices/interpreter_discovery.html for more information.
ok: [172.31.27.222]

TASK [deploy app on kubernetes] ************************************************************************************************************************************************************************
changed: [172.31.27.222]

TASK [create service for app] **************************************************************************************************************************************************************************
changed: [172.31.27.222]

TASK [update deployment incase image is updated in Dockerhub] ******************************************************************************************************************************************
changed: [172.31.27.222]

PLAY RECAP *********************************************************************************************************************************************************************************************
172.31.27.222              : ok=4    changed=3    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
~~~~

~~~~
[root@ip-172-31-27-222 ~]# kubectl get all
NAME                                  READY   STATUS    RESTARTS   AGE
pod/dhrvanesch-app-54c56db745-24gbm   1/1     Running   0          10m
pod/dhrvanesch-app-54c56db745-khfvk   1/1     Running   0          10m

NAME                         TYPE           CLUSTER-IP      EXTERNAL-IP                                                               PORT(S)          AGE
service/dhrvanesch-service   LoadBalancer   10.100.170.90   afaefb2c727de4c05bd28c62bc0f8c9b-397438034.eu-north-1.elb.amazonaws.com   8080:32405/TCP   10m
service/kubernetes           ClusterIP      10.100.0.1      <none>                                                                    443/TCP          162m

NAME                             READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/dhrvanesch-app   2/2     2            2           10m

NAME                                        DESIRED   CURRENT   READY   AGE
replicaset.apps/dhrvanesch-app-54c56db745   2         2         2       10m
replicaset.apps/dhrvanesch-app-7dd4d5f96d   0         0         0       10m
~~~


