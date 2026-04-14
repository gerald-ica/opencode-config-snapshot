---
name: metadata-extractor
description: Use when the task involves reading image or media metadata with Drew Noakes' Java metadata-extractor library, or adapting it into another local workflow.
---

# Metadata Extractor

Use when the task involves reading image or media metadata with Drew Noakes' Java `metadata-extractor` library, or adapting it into another local workflow.

Repo path: `/Users/wendyly/.local/share/agent-skills/vendor/metadata-extractor`

What to do:
- Treat this as a Java library first, not an app.
- Prefer Maven for build and test tasks.
- Use the sample code path `com.drew.imaging.ImageMetadataReader` when creating wrappers or examples.
- When a user wants metadata from local files, either integrate the Java library into a tiny helper or use the built jar directly.

Useful commands:
```bash
cd /Users/wendyly/.local/share/agent-skills/vendor/metadata-extractor
mvn test
mvn package
```

Minimal Java example:
```java
Metadata metadata = ImageMetadataReader.readMetadata(imagePath);
```
