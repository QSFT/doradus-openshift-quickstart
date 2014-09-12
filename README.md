doradus-openshift-quickstart
============================
1. Creating Doradus DIY Application:
rhc app create doradusdemo diy

cd doradusdemo

2. Pulling the code from Github:
git remote add upstream https://github.com/TraDuong1/doradus-openshift-quickstart

git pull -s recursive -X theirs upstream master

3. Pushing the code to OpenShift:
git push

4. Testing:
rhc port-forward

curl 127.0.0.1:1105/_applications
