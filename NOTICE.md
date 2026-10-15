# Origin, licenses and changes — 2026-10-14

Matte18 Direct is an experimental adaptation of the **appearance keys** used by
[Nugget by leminlimez](https://github.com/leminlimez/Nugget) and
[GoldenNugget by awesomenull-dev and GoldenNugget-Team](https://github.com/GoldenNugget-Team/GoldenNugget).
It is not an official release of either project. GoldenNugget's restore backend,
UI, logos and icon assets are not included. The desktop UI and merge/undo engine
were written for this project. Code is provided under the included AGPL-3.0;
MIT third-party files retain their original licenses.

Source snapshots:

0.6.2-test1 additionally includes unmodified Nugget backup encoders
`src/restore/backup.py` and `src/restore/mbdb.py` from commit
`26e0c50ec114ca3a4ff6ab2fb4ae309abfd39fa1` as `vendor/nugget_backup/`.
They are licensed under AGPL-3.0; see `vendor/Nugget-LICENSE`.
The managed home-indicator experiment uses a newly written bounded
MobileBackup2 workflow. It does not include Nugget's path-traversal exploit,
BookRestore, or crash-on-purpose records. This optional experiment DOES
restore one managed preference file; other appearance operations retain
their separate Airlift implementation. Older no-restore descriptions do
not apply to the new home-indicator experiment. Complete application
source is included in each binary package and in a separate source ZIP.

| Source | Commit | Used for |
| --- | --- | --- |
| leminlimez/Nugget | `26e0c50ec114ca3a4ff6ab2fb4ae309abfd39fa1` | Research of keys/compatibility |
| GoldenNugget-Team/GoldenNugget | `69df706a03ee7b4b89ddc305c9a1f2ee71582e99` | Appearance key names and version bounds |
| YiHoooong/AirliftSilence | `552384025ec9782c472a8dcf152e965452567424` | `vendor/airlift_windows.py`, MIT |
| Mak5er/AirCard | `52ba05dca4bdc590672c19d554701f4438e20338` | `vendor/airtraffic_host.m`, MIT |

Changes to vendor files are marked in the source: Windows read-recovery capture,
connection cleanup, recoverable Media-path error; macOS public Grappa host token.
These changes were not tested with the Apple frameworks or a physical phone.

The Windows transport is only used for generic file operations. Matte18 does
not alter call-recording audio or Wallet data. Airlift originates with
[Johnny Franks / 0xjohnnydev](https://github.com/0xjohnnydev/airlift);
the Windows port originates with [Guy Dahan](https://github.com/DahanGuy/airlift-windows).
The Grappa handshake information was published in AirCard-iOS and AirliftSilence.
Keep `vendor/AirliftSilence-LICENSE` and `vendor/AirCard-LICENSE` when redistributing.

Original GoldenNugget credits, retained with attribution:

- awesomenull — lead developer.
- Wind0ws11Aero — development assistance.
- gNugget-i18n contributors — crowdsourced translations.
- LeminLimez — Nugget.
- 0xjonhnnydev [upstream spelling] / 0xjohnnydev — AirLift.
- Legacy Nugget POEditor translation contributors.
- PosterRestore — PosterBoard assistance.
- dootskyre, Middo, dulark, forcequitOS and pingubow — Nugget contributions.
- Snoolie — aar handling.
- iTechExpert — SpringBoard/Internal options.
- Mikasa-san — Quiet Daemon.
- pymobiledevice3 contributors — device algorithms.
- PySide6 contributors — GUI library.

PySide6 and pymobiledevice3 are separately installed dependencies, not authored
by this project. Their own licenses and third-party notices apply to bundled
binary distributions. Compiled/standalone preview apps are supplied separately
from the source archive. They embed official CPython and PySide6 binaries; the
included Windows launcher is cross-compiled from `tools/windows_launcher.c`.
The macOS shell launcher selects an included native arm64 or x86_64 interpreter.
The separate build report records the upstream runtime hashes and versions.

0.3.0-alpha.1 modifications: shared ctypes CoreFoundation/AirTrafficHost loading
on macOS and Windows, explicit void return signatures, retained Windows DLL
search handles, missing manifests fail explicitly, isolated timed sync child,
native-library preflight, persistent recovered-file versions, tester reports.
Standalone apps now include a subset of official pymobiledevice3 dependencies
required by discovery/AFC/diagnostics. Intel Mac cryptography is pinned to 48.0.1
because later releases no longer provide a compatible Intel wheel. Bundled
native execution and physical device effects remain untested.

0.3.1 corrective changes: proper pymobiledevice3 AFC async contexts and streaming
closure; durable pre-read device journals/original capture; error-preserving
cleanup; Windows cache recovery and supervised launch/local DLL diagnostics;
independent Apple Application Support library lookup; read-only USB checks.
No full design/native icon compatibility is claimed; release is not qualified.

0.4.0 artwork: 39 standard light PNGs from catwithabaloon/iOS-18-icon-pack
release 2.0, copied without pixel edits. Exact archive SHA256 and source link
in assets/classic-light/pack.json and NOTICE.txt. Source repository license
retained as SOURCE-LICENSE. Apple artwork/trademarks remain with their owners;
no authentication of extraction or grant of new artwork rights is claimed.
The fixed numbered-file mapping applies only to that exact release hash.

0.5.0: WebClip Info.plist format follows GoldenNugget/Cowabunga, using a
new owned namespace and precomposed flag; direct delivery, journals and GUI
were implemented here. No GoldenNugget restore backend is used.30 icons from
release Beta upgrade/add to the original2.0 set, yielding42 light images.
Per-file dimensions/source/SHA in assets/classic-light/pack.json. PNGs unchanged.
Material parameters/reference symbols are described in MATERIAL_DEVELOPMENT.md.

0.6.3-test1 replaces USB screenshot preview with bundled Apple stock wallpaper images supplied by iClarified. Original article and asset URLs and SHA-256 values are recorded in assets/wallpapers/SOURCES.json. The display selects iOS 18, 26 or 27 by major version; it never reads the personal wallpaper or installs these assets on the phone.
