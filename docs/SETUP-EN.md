# WeloRply — step-by-step installation

**Beta v0.12.4.** The download is named **WeloRply.zip**. Chrome currently displays the extension as **Welo Reply**. They are the same application.

You will install two separate components: the Welo Chrome extension, and Ollama with a local model. The model is downloaded separately; it is not inside the extension ZIP.

## Before starting

Use current desktop Chrome. Ollama requires Windows 10 22H2+ or macOS 14+. The Mac helper also requires Node.js 22+. An 8 GB RAM machine with a small model is a starting target; 16 GB is recommended, not a tested minimum guarantee. Allow roughly 10 GB of free space initially; larger models need more. This package is not for phones or tablets.

The Mac helper has not been tested on real Mac hardware. Helper installers are unsigned. This is a beta.

## 1. Download and extract

1. [Download WeloRply.zip](https://github.com/welosu06/WeloRply/raw/refs/heads/main/WeloRply.zip).
2. Find it in Downloads. Do not use GitHub's green **Code → Download ZIP** button; that downloads the repository wrapper rather than this installable package.
3. On Windows, right-click the ZIP and select **Extract All**. On Mac, double-click it to extract.
4. Put the extracted files in a permanent folder, such as **Documents/WeloRply**.
5. Open that folder. You should see `manifest.json`, `panel.html`, `background.js`, and a `setup` folder.

Opening a ZIP to browse its contents is not the same as extracting it. Keep the extracted folder after installation; do not move or delete it.

## 2. Add the extension to Chrome

1. Type `chrome://extensions` into Chrome's address bar and press Enter.
2. Turn on **Developer mode** at the top right.
3. Click **Load unpacked**.
4. Select the extracted folder containing `manifest.json`, then click **Select folder / Open**.
5. Confirm **Welo Reply**, version **0.12.4**, is listed and enabled.

If Chrome reports a missing manifest, select the inner folder that directly contains `manifest.json`. Select the folder, not the JSON file or ZIP.

## 3. Open the side panel

1. Click Chrome's puzzle-piece **Extensions** button.
2. Pin **Welo Reply**, then click its toolbar icon.
3. Welo opens on the right without navigating away from your X page.
4. Select **EN · English** at the top.
5. Click **Setup**. Setup appears inside the side panel; **Back** returns home.

Official download links can open separate tabs when you click them.

## 4A. Windows setup

1. Open the [official Ollama Windows download](https://ollama.com/download/windows), download the installer, and complete installation.
2. Open Ollama from the Start menu.
3. Optionally click **Download the helper setup package** in Welo. Extract that ZIP as well.
4. Right-click the extracted `Setup.ps1` file. Select **Show more options → Run with PowerShell** if needed.
5. The extension ID is prefilled. Click **Kur ve baslat** (Install and start).
6. After the success message, return to Welo and click **Check setup**. If needed, click **Repair connection / Start Ollama**.

The helper registers to run when you sign in to Windows. Repairs may restart Ollama and interrupt other Ollama requests. If Windows blocks the unsigned helper, do not disable security protections; use the manual method below.

## 4B. Mac setup

1. Download [Ollama for Mac](https://ollama.com/download/mac). Open the disk image, drag Ollama into **Applications**, and open it.
2. To use the helper, install **Node.js 22 or newer LTS** from the [official Node.js website](https://nodejs.org/en/download). Choose the installer for your Mac's Apple Silicon or Intel architecture.
3. Download Welo's helper package and extract it.
4. Open **Applications → Utilities → Terminal**.
5. Type `bash` followed by one space. Do not press Enter yet.
6. Drag the extracted `Kur.command` file into Terminal to insert its path, then press Enter.
7. Wait for setup to finish. Return to Welo and click **Check setup**.

If a component is missing, install it from its official website and try again. For a persistent 403 on Mac, quit Ollama from its menu, then use Welo's repair button. Do not disable system security protections. The helper is not notarized or verified on real Mac hardware yet.

## 5. Connect without the helper

1. Install Ollama first, then fully quit it using its system-tray or menu-bar **Quit** action. Merely closing the app window may leave it running.
2. In Welo, open **Settings → Connection help → Copy commands**.
3. Open **PowerShell** from Windows Start, or **Terminal** on Mac.
4. Paste the copied commands and press Enter. The commands contain your extension's ID and are tailored to your operating system.
5. Leave the terminal open. Return to Welo and refresh the connection.

If you see “address already in use,” another Ollama server is running. Quit that instance rather than starting a second server on the same address.

You should see **Connected**. If there is no installed model, continue below.

## 6. Download a model

1. Open **Models** or click **+ Download / install a model**.
2. Start with **Qwen 3.5 · 0.8B** if you want a small initial download.
3. Click **Download and use**. A separate installation tab opens; click its download button if prompted.
4. Keep that tab open until the model-ready message appears.
5. Return to Welo. The model should be selected automatically. Use **↻** if necessary.

Smaller models can make grammar, language-selection, or meaning errors. Download size is not runtime RAM usage.

## 7. Test without posting

1. Open **Settings → Test the local model**.
2. Enter a short sample post.
3. Click **Generate a reply only**.
4. Wait for a response below the input. The first model load can take longer.

This test sends nothing to X. Get this working before trying actual replies.

## 8. Use on X

1. Sign in to X and refresh the page.
2. Find a text post. Hover over Welo's buttons below it to see their descriptions.
3. Start with **Generate a reply and open as draft**. Read the draft; use X's Reply button yourself if you want to publish it.
4. **Generate and send a reply now** is a separate action that publishes a reply and may use a separate task tab.
5. Select a tone and purpose in **Writing**. Changing TR/EN changes the interface; replies still aim to follow the post's language.

## 9. Link queue

1. Copy an X post URL and paste it into **Add links manually**. Put one link per line.
2. Click **Add links** and check the list.
3. Click **Start**. This sends replies automatically to listed posts.
4. Keep Chrome and the side panel open. Keep the computer awake and do not interact with the task tab's reply editor.
5. Links are removed after a successful send response; the queue advances to the next. Links added during processing are included.
6. **Stop** requests cancellation of remaining work; it cannot undo an already published reply.

The queue waits for the final reply result. A remaining failed link produces an **Incomplete** status. Model failures before sending are retried once. Uncertain sends are not automatically retried: check X first to avoid a duplicate. The status area reports the current stage; an unresponsive task eventually stops with an error.

## 10. Update an existing installation

1. Stop the queue and check any active send result.
2. Download the new ZIP and extract it to a temporary folder.
3. Copy its contents into the same permanent extension folder you originally loaded. Replace matching files; do not nest a new folder inside the old one.
4. Open `chrome://extensions`, click Welo's **Reload** button, and verify version **0.12.4**.
5. Refresh open X tabs, then close and reopen the side panel.

Do not remove the extension merely to update it; removal may erase settings. This GitHub installation does not update automatically.

## Troubleshooting

| Problem | What to do |
| --- | --- |
| Missing manifest | Extract the ZIP and select the folder directly containing manifest.json. |
| No toolbar icon | Pin Welo from Chrome's Extensions menu. |
| Not connected | Open Ollama and refresh, or use Repair connection. |
| 403 | Try repair; otherwise follow the manual connection method above. |
| No model | Download and select a local model. |
| Model timeout | Try a smaller model, close heavy apps, and repeat the local test. |
| Extension context invalidated | Refresh X and reopen the Welo panel. |
| Post opens but nothing happens | Read the current stage under Status and progress. Model loading or your pacing delay may still be running. Record the exact eventual error. |
| Final link remains | Check the extension version and whether a reply exists on X. Report the status/error text. |
| Reply text mismatch | Inspect the draft and verify whether anything was sent before retrying. |
| Previous send recorded | Check X first. Enable repeat replies only if another reply is intentional. |

[Report a problem in Issues](https://github.com/welosu06/WeloRply/issues). Include OS, Chrome version, Welo version, model name, and exact error text. Remove personal data from screenshots. Never share passwords, session cookies, tokens, or private conversations.

## Data and beta limitations

Generation requests go to local Ollama at `127.0.0.1:11434`. Settings and operation records use Chrome's local extension storage. Downloads, external links, and X actions require internet. This build has no Welo licensing server or paid AI API integration.

Comprehensive live-X validation is pending. The precise cause of a reported final-link stall on a user's machine is not yet verified. Recent fixes passed simulated tests; they are not a guarantee on every device.

Follow [X's automation rules](https://help.x.com/en/rules-and-policies/x-automation). Features such as automated likes and website automation may conflict with those rules. No account-safety or engagement guarantees are made. Ollama and individual models have their own licenses.
