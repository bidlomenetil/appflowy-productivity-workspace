# AppFlowy

## Source development guide

### Product and architecture

A local productivity workspace for pages, structured data and collaborative work.

Flutter UI and Dart packages are under `frontend/appflowy_flutter`; Rust workspace code under `frontend/rust-lib` supports native data and workspace operations. Native platform projects are part of the Flutter tree.

### Requirements and local development

Flutter/Dart and Rust toolchains compatible with the checked-in manifests; platform SDKs for the intended desktop or mobile target.

Run these commands from the repository root unless a `cd` is shown:

```sh
cd frontend/appflowy_flutter
flutter pub get
```

These are source-defined entry points. Full dependency installation and service startup were not run during the portfolio maintenance audit; successful application deployment is not claimed.

### Environment configuration

Inspect `frontend/appflowy_flutter` and the component-specific environment templates before startup. Supply local database, service URLs and integration credentials through untracked environment files or a secret manager. Do not copy production credentials into tracked files.

### Testing

```sh
cd frontend/appflowy_flutter
flutter test
```

The full application suite requires the dependencies and services described above. Shell changes in this maintenance pass were checked separately with syntax and mocked command tests; that does not replace integration testing.

### Deployment and integrations

Start with `codemagic.yaml` and review image versions, persistent data paths, authentication, exposed ports and backups before production use. Integration implementations and configuration are in the source directories described above; generated API clients must stay in sync with server contracts.

### Source provenance and license

Imported from [AppFlowy-IO/AppFlowy](https://github.com/AppFlowy-IO/AppFlowy); upstream functionality and copyright belong to the original contributors. Local Git history begins with a 2026 source snapshot import, not historical authorship. The exact imported upstream revision is unknown. The upstream GitHub repository was created on 2021-06-16; the local year directory is organizational metadata.

Read [LICENSE](LICENSE) and nested license/notice files before redistribution; enterprise and bundled third-party components may use different terms. Restored root license text was retrieved verbatim from the official upstream repository during this maintenance pass.
