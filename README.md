Pre-Req:
- account on github.com 

1. Once receive an email invitation to the Meraki lab organization
2. Get your own Meraki Dashboard API key
3. Grab the serial numbers from the Network notes of the pre-deployed Datacenter network    
4. Create your own git and clone/fork the repo 
5. Add API key in enviromental secrets on newly created repo
6. Replace serials and Org Name in .env
7. Evaluate configs
8. Run "Deploy Small Branch as Code" workflow
9. Read explanation what happens in every step of the workflow
10. Navigate to Meraki Dashboard to see created networks, vpn status..
11. Go to the workflow and look in the artifacts 
12. Evaluate Automatic tests.
13. Syntax 
   - run Syntax action
   - go to schema and change org name field to max 128 change to max 10 -->
            ```
            organizations:
                  name: str(min=1, max=128, required=False)
            ```      
   - re-run syntax check (that shall fail)
 
14. Semantics 
   - run Semantics action
   - go to org_global.nac.yaml and change admin name to root
         ```
            meraki:
               domains:
                  - name: US
                      administrator:
                            name: admin ---> here change to root
                    organizations:
         ```
         
   - there is a semantic (= business) rule that does not allow admin name in my company to be "root"
   - run semantic action again (that shall fail)

14. Evaluate automatic tests -> show the log and all the executed tests
   - showcase the scheduled cron job (will run every 6hrs). How to handle the pod going down after reservation.?
