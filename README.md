# Godot encrypted templates build

Builds the Godot 4.7 export templates with script encryption for NoruCore.
The key is a repository secret (`SCRIPT_AES256_ENCRYPTION_KEY`).

The Linux template is built on Ubuntu 22.04 (glibc 2.35).

Artifacts are encrypted to `artifact_cert.pem`, since a template carries the key.
Decrypt locally:

```sh
openssl cms -decrypt -binary -inform DER -in FILE.gz.p7 -inkey artifact_key.pem | gunzip > FILE
```
