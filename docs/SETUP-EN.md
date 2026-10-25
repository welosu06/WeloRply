# WeloRply — step-by-step installation

**Beta v0.12.6.** The download is named **WeloRply.zip**. Chrome currently displays the extension as **Welo Reply**. They are the same application.

You will install two separate components: the Welo Chrome extension, and Ollama with a local model. The model is downloaded separately; it is not inside the extension ZIP.

## Before starting

Use current desktop Chrome. Ollama requires Windows 10 22H2+ or macOS 14+. The Mac installer automatically downloads and verifies Node.js 22 when needed. An 8 GB RAM machine with a small model is a starting target; 16 GB is recommended, not a tested minimum guarantee. Allow roughly 10 GB of free space initially; larger models need more. This package is not for phones or tablets.

The Mac fixes were exercised on a real user device, and all three models were checked with local generation. Helper installers are unsigned. This remains a beta; run the no-post test before using it on X.

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
5. Confirm **Welo Reply**, version **0.12.6**, is listed and enabled.

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

## 4B. Easy Mac setup

1. Download Ollama from the [official Mac page](https://ollama.com/download/mac).
2. Open the download, move **Ollama** into **Applications**, and open it once.
3. In Welo, choose **Setup → Download the helper setup package**. Alternatively, open **setup/welo-mac.zip** inside the main package; it is the same helper.
4. Extract the helper ZIP too. The extension ZIP and helper ZIP are separate archives.
5. Double-click **Kur.command** in the newly extracted helper folder. A Terminal window opens; you do not need to type a command. Use this new copy, not an old Downloads folder with a suffix such as `(2)` or `(3)`.
6. Wait for setup messages. If needed, Node.js is downloaded from its official source and its SHA-256 checksum is checked. Keep your internet connection available.
7. If prompted to quit Ollama, use the **Ollama icon in the Mac menu bar → Quit**. Closing only the app window does not stop the server. Let any other active model task finish first.
8. Return to the installer Terminal and press **Enter**. Setup checks the connection and starts Ollama as needed.
9. Wait for **Kurulum tamamlandi** (Installation completed). Press Enter to close the installer.
10. Return to Welo and click **Check setup**. Use **Repair connection / Start Ollama** if needed.
11. If no model is installed, proceed to section 6. If you already have one, select it without downloading it again.

**Window-based alternative:** Open **Welo Kurulum.app** from the same folder and choose **Kur (Install)**. If it asks you to quit Ollama, follow step 7 and choose **Devam (Continue)**. Run only one installer at a time.

**If macOS blocks opening:** Confirm the file came from this repository. After trying to open it, check **System Settings → Privacy & Security** for the file-specific **Open Anyway** option. These installers are not Apple-signed or notarized. Do not turn off system-wide protections. If no file-specific option is available, use the manual method below.

**“Microsoft Edge yardimcisi atlandi (EPERM)”** means Edge registration was skipped. Chrome installation continues; read the final result. It does not prevent Chrome setup.

After a successful helper installation, Terminal does not need to stay open. The manual method below is different.

## 5. Connect without the helper

1. Install Ollama first, then fully quit it using its system-tray or menu-bar **Quit** action. Merely closing the app window may leave it running.
2. In Welo, open **Settings → Connection help → Copy commands**.
3. Open **PowerShell** from Windows Start, or **Terminal** on Mac.
4. Paste the copied commands and press Enter. The commands contain your extension's ID and are tailored to your operating system.
5. Leave the terminal open. Return to Welo and refresh the connection.

If you see “address already in use,” another Ollama server is running. Quit that instance rather than starting a second server on the same address.

You should see **Connected**. If there is no installed model, continue below.

## 6. Download a model

**One model is enough; you do not need all three.**

| Model | Approximate download | Choice |
| --- | --- | --- |
| Qwen 3.5 · 0.8B | 1.2 GB | Small Qwen option, including the Mac language fixes. |
| Qwen 3.5 · 2B | 2.7 GB | Larger Qwen option; may use more memory. |
| Gemma 3 · 1B | 806 MB | Lightweight alternative; existing generation behavior preserved. |

Sizes can vary by model revision and device. **0.8B is not 0.08B.** Larger models do not guarantee a better result for every post.


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
5. English sample: “The new offline editor saves drafts on your device so you can keep writing without an internet connection.” Check that the reply is English.
6. Turkish sample: “Yeni çevrimdışı editör taslakları cihazına kaydediyor, böylece internet bağlantısı olmadan da yazmaya devam edebiliyorsun.” Check that the reply is Turkish.
7. Select each other model you intend to use and repeat. TR/EN changes the interface, not the intended reply language.

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
4. Open `chrome://extensions`, click Welo's **Reload** button, and verify version **0.12.6**.
5. Refresh open X tabs, then close and reopen the side panel.

If an older Mac helper is installed, extract the new **setup/welo-mac.zip** and run its installer once to update it. If you already installed the v4 helper and the connection works, there is no need to reinstall it. Keep your existing model downloads.

Do not remove the extension merely to update it; removal may erase settings. This GitHub installation does not update automatically.

## Troubleshooting

| Problem | What to do |
| --- | --- |
| Missing manifest | Extract the ZIP and select the folder directly containing manifest.json. |
| No toolbar icon | Pin Welo from Chrome's Extensions menu. |
| Not connected | Open Ollama and refresh, or use Repair connection. |
| 403 | Try repair; otherwise follow the manual connection method above. |
| Edge skipped / EPERM | Chrome setup continues; check the final completion message. |
| Ollama / User cancelled (-128) | Use the latest Mac helper. Quit Ollama from its menu bar icon, then press Enter / Continue in the installer. |
| Reply language does not match | Confirm version 0.12.6, refresh X and reopen Welo. Test the selected model locally; report the model and sample post if it persists. |
| Node.js download failed | Check the connection and retry the new installer. Read the installation log for details. |
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

In the October 25, 2026 Mac check, Qwen 0.8B and 2B replied in the expected language for English and Turkish examples. Gemma 1B worked for the English example but replied in English to one Turkish sample. Review drafts before posting. The user confirmed the latest package works; this does not guarantee every device or post. Comprehensive live-X testing is not claimed.

Follow [X's automation rules](https://help.x.com/en/rules-and-policies/x-automation). Features such as automated likes and website automation may conflict with those rules. No account-safety or engagement guarantees are made. Ollama and individual models have their own licenses.

Official requirements: [Ollama Mac](https://ollama.com/download/mac), [Ollama Windows](https://github.com/ollama/ollama/blob/main/docs/windows.mdx).
