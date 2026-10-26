# Diwali Wall: share a wish, light a diya

Phones send wishes. The main screen lights one diya per wish (400 in total) and shows the wishes as they arrive.

| Page | Link | Who uses it |
|---|---|---|
| Wish page (QR goes here) | `https://<your-site>/` | Everyone, on their phone |
| Main screen | `https://<your-site>/#screen` | The person presenting |
| Moderation | `https://<your-site>/admin?key=<ADMIN_KEY>` | Host only. Keep private |

## Main screen controls (move the mouse to show them)
- **Full screen** (key **F**)
- **Final reveal** (key **R**): lights every remaining diya, centre outward
- **Wish page** (key **W**): every wish received, newest first. Press again, or **Esc**, to return
- Click a wish on the right to hide it from the screen

## Files (everything the site needs)
`index.html` (all pages and design), `server.js` (stores and serves wishes), `package.json`, `render.yaml` (hosting recipe), `.gitignore`

## Run on your laptop
Needs Node 18 or newer. No install step.

    node server.js

Open `http://localhost:3000/#screen`. The terminal prints the moderation link.

## Host free on Render
1. Put these files at the top level of a GitHub repo.
2. render.com > **New > Blueprint** > pick the repo > **Apply**.
3. Your link appears on the service page. `ADMIN_KEY` is under **Environment**.
4. Check `https://<your-site>/api/health`.

## Free-tier notes
- The service sleeps after 15 idle minutes and takes about a minute to wake. Open the main screen 10 minutes before the event and leave it open.
- A redeploy or restart clears saved wishes. Upload changes before rehearsal, never during the event.
- Wishes are stored on the host (outside company systems). Get approval and delete the data after the event.

## Changing things
- Wording and design: `index.html`
- Number of diyas: the `RINGS` list in `index.html` (currently 400)
- Wish length: `MAX_LEN` in both `index.html` and `server.js`
