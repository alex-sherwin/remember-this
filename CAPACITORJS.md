# Secure Context (OPFS / SharedArrayBuffer)

Impossible.

CapacitorJS uses a custom URI scheme handler like `capacitor://` for handling loading statically bundled files into the WKWebView.

This is normal, it's the same thing e.g. RN, Expo, Tauri do.

Unfortunately iOS reserves `http://`, `https://` and `file://` (obviously) so custom scheme handlers can't use this.

But based on the requirements for Secure Context browsing (see MDN docs), only TLS secured or localhost via `http://`, `https://` or `file://` are eligible ways to enable Secure Context.

Thus, it is seemingly impossible at this moment (2024-12-11) to get OPFS properly working in a web based framework like CapacitorJS

