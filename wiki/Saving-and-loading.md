[My Mind](https://mercurial.top/my-mind) supports saving and loading to a number of storage backends with different feature sets. There is a dedicated UI pane for these operations, available via the **Save/Save as/Load** buttons (or **Ctrl+S/Ctrl+Shift+S/Ctrl+O** keys).

Once you save or load a map, the currently used backend name is stored in the URL, as well as the map id. This permalink can be used to link to a saved map.

### File formats
Some storage backends allow working with multiple file formats: native MyMind format, MindMup JSON, FreeMind XML and MindMap Architect XML. These can be both loaded and saved.

You can save your map in a simple, tab-indented plaintext file. Re-loading this file works, but will obviously result in loss of certain metadata.

The "Save" dialog also allows you to [[save the map as an image|Creating map images]], although it is now preferred to [[create the image locally using Firefox Devtools|Saving-images-client-side]].

### Browser storage
Browsers storage (AKA WebStorage) is a fast way to store maps locally. These maps cannot be shared for obvious reasons.

### Firebase
Maps can be stored in a [[Firebase|https://www.firebaseio.com/]] database. It is up to the user to create and configure a Firebase name, as well as any optional authentication methods.

Maps in Firebase are synced in real-time, which means that multiple users can edit them and their changes will be auto-propagated to all collaborators.

### Google Drive
If you choose this backend, you will be prompted to log-in to Google and allow My Mind to access your GDrive files. Saved maps can be then opened directly from the Google Drive UI; it is also possible to create new maps directly from the Drive.

### File
Local filesystem can be accessed for both reading and writing maps. This backend does not generate permalinks, as it is not (yet?) possible to automatically read local files from within a web browser.

### Generic WebDAV
A generic REST API can be accessed (via GET/POST requests) using this backend. Just specify an URL for HTTP requests. 
