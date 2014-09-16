Doradus on OpenShift Quickstart
===============================

This is a simple Red Hat OpenShift example that demonstrates how to deploy and use Doradus (https://github.com/dell-oss/Doradus) as an OpenShift cartridge.  


Running on OpenShift
----------------------------

Create an account at https://www.openshift.com

Create Do It Yourself (DIY) Application. 
Note that diy is OpenShift keyword. In this example, we will name our application "doradusdemo"

    rhc app create doradusdemo diy

Add this upstream repo

    cd doradusdemo
    git remote add upstream https://github.com/TraDuong1/doradus-openshift-quickstart
    git pull -s recursive -X theirs upstream master


Then push the repo upstream

    git push

Test

    Invoke this URL to list all applications under Doradus
    http://doradusdemo-$yournamespace.$youropenshiftserver/_applications
    
    For the first time, you should expect to see empty list.
    
    Using Rest Client, post this XML schema to create a new application and its tables 
    in Doradus via the URL above
    
     <application name="MyApplication"> 
            <key>Test123</key> 
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
    
    Invoke the URL http://doradusdemo-$yournamespace.$youropenshiftserver/_applications again to see the Doradus the application and its data.

    Read more about REST APIs on the Doradus website.

    

