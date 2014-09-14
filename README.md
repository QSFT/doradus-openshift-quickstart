Doradus on OpenShift Quickstart
===============================

This is a simple Red Hat OpenShift example that will deploy a simple single-instance Cassandra and Doradus (https://github.com/dell-oss/Doradus) 


Running on OpenShift
----------------------------

Create an account at https://www.openshift.com

Creating DIY Application 

    rhc app create doradusdemo diy

Add this upstream repo

    cd doradusdemo
    git remote add upstream https://github.com/TraDuong1/doradus-openshift-quickstart
    git pull -s recursive -X theirs upstream master


Then push the repo upstream

    git push

Test

    rhc port-forward
    http://127.0.0.1:1105/_applications



