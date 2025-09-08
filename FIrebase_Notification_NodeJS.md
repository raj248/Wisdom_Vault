You can send Firebase push notifications from Node.js using the **Firebase Admin SDK**. Here’s a step-by-step guide 👇

---

### 1. Install Firebase Admin SDK

```bash
npm install firebase-admin
```

---

### 2. Initialize Firebase in your Node.js app

You need a **service account key JSON** from your Firebase project (download from Firebase Console → Project Settings → Service Accounts → Generate New Private Key).

```js
const admin = require("firebase-admin");

// Load your service account key JSON
const serviceAccount = require("./serviceAccountKey.json");

admin.initializeApp({
  credential: admin.credential.cert(serviceAccount),
});
```

---

### 3. Send a notification to a device

Each mobile device gets a **Firebase device token** (via the Firebase client SDK on iOS/Android).
You send to that token like this:

```js
const sendNotification = async (token, title, body) => {
  const message = {
    notification: {
      title,
      body,
    },
    token, // device FCM token
  };

  try {
    const response = await admin.messaging().send(message);
    console.log("Successfully sent message:", response);
  } catch (error) {
    console.error("Error sending message:", error);
  }
};

// Example usage
const deviceToken = "DEVICE_FCM_TOKEN"; // Replace with actual token
sendNotification(deviceToken, "Hello 👋", "This is a test notification!");
```

---

### 4. Send to multiple devices (optional)

```js
const message = {
  notification: {
    title: "Sale Alert 🚀",
    body: "50% off on all products today!",
  },
  tokens: ["token1", "token2", "token3"], // array of device tokens
};

admin.messaging().sendEachForMulticast(message)
  .then((response) => {
    console.log(`${response.successCount} messages were sent successfully`);
  })
  .catch(console.error);
```

---

✅ That’s it — the mobile app (iOS/Android) will receive the notification if it’s set up with FCM properly.

---

Do you want me to also show you how to **get the FCM token in your mobile app** (Android/iOS), so you can test this end-to-end?
