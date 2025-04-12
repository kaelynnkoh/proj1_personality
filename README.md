# 🧠 proj1_personality

A playful web app that helps you learn more about your friend (or crush) likes and personality — and then gently ask them out based on their answers! 💜

## 💡 How It Works

The app asks a series of fun questions, stores the answers, and then uses those answers to craft a sweet invitation at the end. It's also connected to Google Forms to collect the responses anonymously (or not, up to you).

---

## 🚀 Getting Started

### 🛠 Customize Your Questions

In `script.js` (or the HTML file if everything’s inline), you’ll find a section like this:

```js
const questions = [
  { question: "What's your favorite food?", key: "food" },
  { question: "What's your idea of a perfect date?", key: "date" },
  { question: "Dogs or cats?", key: "pet" },
  { question: "Are you more of a night owl or early bird?", key: "vibe" },
];

Feel free to change the questions and keys to whatever you want! Just remember to update your Google Form to match.
```
### 🧾 How to Connect to Your Own Google Form

1. Create a **Google Form** with the same questions as your app.
2. Click the ⋮ (three-dot menu) in the top-right corner and select **“Get pre-filled link.”**
3. Fill in some **dummy answers** and click **“Get link.”**
4. Copy the **pre-filled link**. It’ll look something like this:
https://docs.google.com/forms/d/e/1FAIpQLSfABC123XYZ/viewform?usp=pp_url&entry.123456=...
5. Note the `entry.xxxxxx` IDs for each question — these are the **keys** you’ll need for your code.
6. Open the `sendToGoogleForm()` function in your JavaScript and modify it like this:

```js
function sendToGoogleForm() {
  const formUrl = 'https://docs.google.com/forms/d/e/YOUR_FORM_ID/formResponse';
  const data = new URLSearchParams();

  data.append('entry.123456', answers.name || '');
  data.append('entry.654321', answers.food || '');
  // etc...

  fetch(formUrl, {
    method: 'POST',
    mode: 'no-cors',
    body: data
  });
}
```
### 🧙‍♂️ Bonus Features

🌙 If the user says they’re a night owl, the invitation will suggest going out “at night”; otherwise, “in the morning.”
🐶 If the user prefers dogs or cats, the background theme adjusts subtly.

Built with curiosity and low-key romantic energy 💌
Inspired by real friendships and tiny crushes.




