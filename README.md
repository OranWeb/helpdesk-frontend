# helpdesk-frontend
Really simple helpdesk frontend that submits data into webhook.

The default password is helloworld

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

Released under MIT License to help out forward thinking companies and agencies to manage their IT subsystems. 
