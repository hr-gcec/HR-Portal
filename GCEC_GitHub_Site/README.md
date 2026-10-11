# GCEC Employee Workspace — website files

These files put the GCEC Employee Workspace on GitHub Pages. The dashboard itself
runs on Google (Apps Script), which is what lets it recognise each employee's
@gcecglobal.com account without a login. This site is the front door to it.

| File | What it is |
|---|---|
| `index.html` | The page employees open. It loads the workspace inside your GitHub address. |
| `backend-config.js` | **The only file you edit.** Paste the Apps Script Web App URL here. |
| `gcec-logo.png`, `favicon.png`, `apple-touch-icon.png` | Logo and browser/phone icons. |
| `.nojekyll` | Tells GitHub to publish the files exactly as they are. Leave it in. |

## Publish on GitHub Pages

1. On github.com, create a new repository (for example `gcec-workspace`).
2. Choose **Add file > Upload files**, drag in every file from this folder, and select **Commit changes**.
   (`.nojekyll` is hidden on some computers — if you can't see it, create it on GitHub with
   **Add file > Create new file**, name it `.nojekyll`, and commit it empty.)
3. Open `backend-config.js` on GitHub, select the pencil icon, paste your Web App URL between the
   quotes, and commit.
4. Go to **Settings > Pages**. Under *Build and deployment*, choose **Deploy from a branch**,
   branch **main**, folder **/ (root)**, then **Save**.
5. After a minute or two, GitHub shows your site address (for example
   `https://yourname.github.io/gcec-workspace/`). Share that link with employees.

## Apps Script settings this depends on

In Apps Script, the web app must be deployed with:
- **Execute as:** Me (hr@gcecglobal.com)
- **Who has access:** Anyone within GCEC Global

## How it behaves

- **Chrome and Edge:** the workspace opens inside your GitHub address.
- **Safari, Firefox, iPhone and iPad:** these browsers block Google sign-in inside embedded pages,
  so the site opens the workspace directly on Google instead. Same dashboard, no login.
- **Not signed in to a GCEC Google account:** the site sends the person to Google to sign in first.
- Supervisor view of a team member: add `?view=their.email@gcecglobal.com` to the site address.

The Web App URL in `backend-config.js` is visible to anyone who looks, which is fine: only
signed-in @gcecglobal.com accounts that are listed in the Employees tab can open the workspace.
