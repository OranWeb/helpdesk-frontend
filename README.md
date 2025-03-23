# helpdesk-frontend

## Really simple helpdesk frontend that submits data into webhook.
### Password
The default password is helloworld - YOU SHOULD CHANGE THIS
### Generate Password
to generate SHA256 password copy paste the below code into your browser console (Replace 'your-password-here' with whatever password you want to hash)

    async function generatePasswordHash(password) {
      const encoder = new TextEncoder();
      const data = encoder.encode(password);
      const hashBuffer = await crypto.subtle.digest('SHA-256', data);
      const hashArray = Array.from(new Uint8Array(hashBuffer));
      const hashHex = hashArray.map(b => b.toString(16).padStart(2, '0')).join('');
      return hashHex;
    }
    generatePasswordHash('your-password-here').then(hash => {
      console.log('SHA-256 Hash:', hash);
    });

# Discord/Slack Integration 
Change the webhook url in line 404

# Usage Screenshot
![Usage Screenshot](http://i.oran.pw/images/msedge_9KxicSGLG6.png)
![Usage Screenshot](http://i.oran.pw/images/msedge_s94nNFl3xE.png)

# License
Released under MIT License to help out forward thinking companies and agencies to manage their IT subsystems. 
