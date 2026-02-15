---
title: Troubleshooting
nav_order: 12
---

# Troubleshooting

## “Missing plugin.yml”
Make sure your build is NOT excluding your plugin.yml.

## VerifyError / stackmap frames
Use safe ProGuard settings for plugins:
- `-dontoptimize`
- `-dontshrink`
- `-dontpreverify`

Also ensure ProGuard runs on the final shaded jar.
