# How to install pm2 in ubuntu with nodejs and npm and start your server using pm2 and also auto start on reboot system

### Step 1: Update Your System
```
sudo apt update
```

### Step 2: Install Node.js and npm
1. Install node version manager (nvm) by typing the following at the command line.
```
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
```
We will use nvm to install Node.js because nvm can install multiple versions of Node.js and allow you to switch between them.  
2. Load nvm by typing the following at the command line.
  ```
  source ~/.bashrc
  ```
3. Use nvm to install the latest LTS version of Node.js by typing the following at the command line.
  ```
  nvm install --lts
  ```
Installing Node.js also installs the Node Package Manager (npm), so you can install additional modules as needed.
4. Test that Node.js is installed and running correctly by typing the following at the command line.
  ```
  node -v
  ```

### Step 3: Install PM2 Globally
PM2 is a process manager for Node.js that allows you to run your application in the background also start it automatically when system reboots.
1. Install PM2 using npm:
```
sudo npm install pm2@latest -g
```
2. Verify the PM2 installation:
```
pm2 --version
```

### Step 4: Start Your Node.js Application with PM2
You can use PM2 to run your Node.js application with the npm start command.
1. Navigate to your Node.js application's root directory:
  ```
  cd /path/to/your/application
  ```
2. Start your Node.js application with PM2 using npm start:
  ```
  pm2 start npm --name "your-app-name" -- start
  ```
The `--name` flag allows you to give a custom name to your application in the PM2 process list.


### Step 5: Monitor and Manage the Application
You can now monitor, restart, and manage the application using PM2.
1. List all running processes:
  ```
  pm2 list
  ```
2. Check application logs:
  ```
   pm2 logs
  ```
3. Restart the application:
```
pm2 restart your-app-name
```
4. Stop the application:
  ```
  pm2 stop your-app-name
  ```

### Step 6: Auto-start PM2 on System Boot
To ensure that PM2 starts your Node.js application automatically after a system reboot, you can enable the PM2 startup script.
1. Generate and enable the startup script:
```
pm2 startup systemd
```
2. Save your current PM2 process list:
  ```
  pm2 save
  ```







  
