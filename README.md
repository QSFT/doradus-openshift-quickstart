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

    Port forward all listening ports over SSH:
    rhc port-forward

    On a local machine, when you connect to the local loopback address on port 1105, you actually connect to Doradus on the gear
    http://127.0.0.1:1105/_applications

    Using Rest Client, post this XML schema to create a new application and its tables in Doradus via the URL above
     <application name="MyApplication"> 

            <key>Tra</key> 
            <options> 
                <option name="StorageService">SpiderService</option> 
            </options> 
            <tables> 
                <table name="Movies"> 
                    <fields> 
                        <field name="Name" type="text"/> 
                        <field name="ReleaseDate" type="timestamp"/> 
                        <field name="Cancelled" type="boolean"/> 
                        <field name="Director" type="text"/> 
                        <field name="Leads" type="text" collection="true"/> 
                        <field name="Budget" type="integer"/> 
                    </fields> 
                </table> 
            </tables> 
        </application>
  	



