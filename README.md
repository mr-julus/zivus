# Zivus
Zivus creates a simple API that checks whether a code is valid with Firestore Database. This an example of using Zivus

# Example of use
```javascript
async function checkAccess(key, UID) {
    try {
        const response = await fetch('https://zivus.vercel.app/api/verification', {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json',
            },
            body: JSON.stringify({ key, UID }),
        });
    
        if (!response.ok) {
            throw new Error('Network response was not ok');
        }
    
        const data = await response.json();
        console.log('Access granted:', data.accessGranted);
        return data.accessGranted;
    } catch (error) {
        console.error('Error:', error);
        return false;
    }
}
checkAccess('KEY', 'YOUR UID ; AVAIBLE ON: my.mr-julus.is-a.dev/zivus/get-my-uid');
```
