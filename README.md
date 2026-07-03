# Meeting Scheduler

Static GitHub Pages app for Liu Zijun's research group meeting scheduling.

## Online anonymous counts

The page can run offline, but cross-device anonymous counts need a shared database.
Use Firebase Realtime Database:

1. Create a Firebase project.
2. Add a Realtime Database.
3. Copy the database URL, for example:

   `https://your-project-default-rtdb.firebaseio.com`

4. In Firebase Realtime Database rules, for this lightweight scheduling use case:

```json
{
  "rules": {
    "meetings": {
      ".read": true,
      ".write": true
    }
  }
}
```

5. Open the scheduler page as organizer, paste the database URL, add time slots, then generate the student link.

Students submit anonymously. The page stores only an anonymous browser ID and availability choices.
