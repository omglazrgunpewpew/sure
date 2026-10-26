# Dependency Security Maintenance

## Scope And Requirements

Patch compatible archive, JavaScript and Rust TLS dependencies. Preserve application behavior, tenant boundaries, authorization, schema, provider data and the existing audit policy. Keep the current Tauri/GTK stack, whose glib 0.18 medium advisory remains unresolved.

## Validation

RubyZip 3.7.0 export/import and traversal safety smoke checks passed. Desktop frontend build and npm audit passed. Locked Cargo metadata and dependency checks passed. Local Rails checks are unavailable without the native gem build environment. Local Windows native compilation cannot complete because msvcrt.lib is missing.

The first hosted run on d9db07915dd1cf82ab404374cc97d167e4f64214 passed the desktop native check and JavaScript lint. Its five Ruby jobs stopped before tests because the pinned Ruby installer does not recognize the Ubuntu 26.04 image now selected by ubuntu-latest. Pin those five jobs to Ubuntu 24.04, retaining their commands, services, permissions and timeouts.

## Remaining Gates

Run all hosted Rails, security, JavaScript and native desktop checks on the final candidate. Complete fresh independent review and exact-head remote review before merge. Verify merged-main checks and the remaining GitHub alerts after delivery.