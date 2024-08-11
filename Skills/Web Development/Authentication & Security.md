- Authentication & Security
    
    - 003 Level 1 - Register Users with Username and Password
        - Create Database
        - have `UserSchema` with email and password to be saved
        - /register to create user data
            - res.render(”secrets”)
        - /login to find the user data
            - if correct res.render(”secrets”)
        - If the data base in hacked they will know the user data as we didn’t encrypt
        
    - 005 Level 2 - Database Encryption **mongoose-encryption**
        - /register Before saving the password Encrypt it and save in DB
            - `mongoose-encryption` add plugin
        - /login it will decrypt the password from binary string and check
        
    - 006 Using Environment Variables to Keep Secrets Safe ``**process.env.SECRET**

        - secrets like key, ID, and client ID should not be added publicly.
        - you can use an environment variable `dotenv`
            - with `NAME=VALUE`
        - and gitignore
        
    - 007 Level 3 - Hashing Passwords **md5**
        - to prevent key leaks with encrypting
        - you can use Hashing and you no need a key
        - `npm i md5`
            - `md5(password)` wherever hashing is required
            
    - 008 Hacking 101 976365039
    
        - more string in a password its is exponentially safer.
    - 009 Level 4 - Salting and Hashing Passwords with **bcrypt nvm**
        
        - bcrypt is slower that md5 the crack and its industry standard
            - 20,000,000,000 MD5 Hashes/sec
            - 17,000 bcrypt Hashes/sec
        - `nvm` to downgrade to a stable version of npm.
        
        [bcrypt](https://www.npmjs.com/package/bcrypt)
        
    - 010 What are **Cookies** and **Sessions_**
        - Sessions is cookie for login
        - `npm i passport`
        
    - 011 Using Passport.js to Add Cookies and Sessions
        
        - `npm i passport passport-local passport-local-mongoose passport-session`
        - [https://www.passportjs.org/tutorials/password/](https://www.passportjs.org/tutorials/password/)
        
        [Documentation](https://www.passportjs.org/docs/)
        
        [passport-local](https://www.npmjs.com/package/passport-local)
        
    - 012 Level 6 - **OAuth 2.0** & How to Implement Sign In with Google
        
        - `npm i mongoose-findOrCreate`
        
        [](https://www.passportjs.org/packages/)
        
        [passport-google-oauth20](https://www.passportjs.org/packages/passport-google-oauth20/)
