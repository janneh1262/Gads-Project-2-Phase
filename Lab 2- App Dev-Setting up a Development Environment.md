
## Lab 2: App Dev: Setting up a Development Environment v1.1
  #### Objectives

    ##### In this lab, you learn how to perform the following tasks:

    * Provision a Google Compute Engine instance.
    * Install software on the instance.
    * Connect to the instance using SSH.
    * Verify the software installation.

### Task 1: Perform a query on the data using the bq command
    1. In the Cloud Platform Console, on the Navigation menu, click Compute Engine.
    2. On the VM Instances page, click Create.
    3. On the Create an instance page, for Name type dev-instance, select us-central1 for region and us-central1-a for the zone.
    4. In the Identity and API access > Access Scopes section, select Allow full access to all Cloud APIs.
    5. In the Firewall section, enable Allow HTTP traffic.
    6. Leave the remaining settings as their defaults, and click Create.
       * It takes about 20 seconds for the virtual machine to be provisioned and started.
    7. On the VM instances page, in the row for the dev-instance, click SSH (in the Connect column).

### Task 2: Install software on the VM instance
     1. In the SSH session, to update the Debian package list, execute the following command:

        > sudo apt-get update

     2. To install Git, execute the following command:

         > sudo apt-get install git

         Note:If prompted, press Enter.
     3. To install npm and Node.js, execute the following command:
         > sudo apt install nodejs

### Task 3: Configure the VM to Run Application Software
      
      1. To check the version of Node.js, execute the following command:
         > node -v

      2. To clone the class repository, execute the following command:

         > git clone https://github.com/GoogleCloudPlatform/training-data-analyst

      3. To change the working directory, execute the following command:

          > To change the working directory, execute the following command:
      
      4.  To run a simple web server, execute the following command:

           > sudo node server/app.js

      5. Return to the Cloud Console VM instances list, and click on the External IP address for the dev-instance.

        Note: You should see a Hello GCP dev! message from Node.js.

      6. Return to the SSH window, and stop the application by pressing Ctrl+C.

      7. To install the Node.js library for Compute Engine, execute the following command:

           > npm install 

           Note: Run sudo apt-get install npm if prompted npm not available

      8. To run a simple Node.js application that lists Compute Engine instances, execute the following command:

          > node list-gce-instances.js

          Note: Many details about your machine should appear in the terminal window.
