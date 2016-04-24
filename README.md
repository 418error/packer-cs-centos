# packer-cs-centos

Basic packer configuration to create default images for Vagrant

Usage:

Validate the template - this checks the syntax and configuration of the template

```$ packer validate packer.json```

```$ packer build packer.json```

Notes:

  1. The version of Guest Additions running on the build machine must match the version being installed into the packer        image, otherwise you'll get a checksum error and the build will fail.

  2. Any iso images failing a checksum error (OS or Gurst Additions) get deleted automatically by packer, Store copies of the isos elsewhere before the build to avoid the need to download them again.

  3. This requires v 1.7.4 of Vagrant to build, a bug means that the biosdevname package is required when it shouldn't be when reverting to old style interface names e.g. eth0.
