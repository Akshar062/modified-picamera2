# Picamera2

---
*Picamera2* is currently available here as a beta release. This means there may still be some issues and bugs which we shall work on fixing, and where users identify particularly useful features we may still consider implementing them. Mostly we shall be working on bugs, stability, support, examples and documentation, as well as keeping up with ongoing _libcamera_ development. There will also be quite a strong presumption _against_ making signficant code changes unless it seems absolutely necessary, especially any that break existing behaviour or APIs.
---

*Picamera2* is the libcamera-based replacement for *Picamera* which was a Python interface to the Raspberry Pi's legacy camera stack. *Picamera2* also presents an easy to use Python API.

You can find [documentation here](https://datasheets.raspberrypi.com/camera/picamera2-manual.pdf) which should help you to get started.

There are also many examples in the `examples` folder of this repository, and some further _Qt_ application examples in the `apps` folder.

## Installation

_Picamera2_ is only supported on Raspberry Pi OS Bullseye (or later) images, both 32 and 64-bit. As of September 2022, _Picamera2_ is pre-installed on Raspberry Pi OS images, but not on Raspberry Pi OS Lite images. It works on all Raspberry Pi boards right down to the Pi Zero, although performance in some areas may be worse on less powerful devices.

_Picamera2_ is _not_ supported on:

* Images based on Buster or earlier releases.
* Raspberry Pi OS Legacy images.
* Bullseye (or later) images where the legacy camera stack has been re-enabled.

On systems where _Picamera2_ is supported but not pre-installed, you can install it with
```
sudo apt install python3-picamera2 --no-install-recommends
```
to get a slightly reduced installation with fewer of the window system related elements (this would be suitable for installing on a Raspberry Pi OS Lite system), or
```
sudo apt install python3-picamera2
```
for a full installation.

_Picamera2_ can be installed using `pip`, however, we recommend installing through `apt` as this guarantees you will get versions of _Picamera2_ and the underlying _libcamera_ libraries that have been confirmed as working together.

## Contributing

Please note that the "main" branch of this repository corresponds to the currently released version of _Picamera2_ so that the examples there can be referred to by users. Development for forthcoming releases happens on the "next" branch.

We are happy to receive pull requests (normally for the "next" branch) that will fix bugs, add features and generally improve the code. Pull requests should be:

- Restricted to one change or feature each. Please try to avoid "drive-by fixes" especially in a larger set of changes, as it can make them harder to review.
- The commit history should consist of a number of commits that are as easy to review as possible. In particular this means:
  - Where one commit is fixing errors in an earlier commit in the set, please simply merge them.
  - Where a commit is reverting a commit from earlier in the set, please remove the commit entirely.
  - Please avoid adding merge commits or any other unnecessary commits.
  - The commit message should have a short single line at the top which is nonetheless as descriptive as possible. After that we encourage more lines explaining in a little more detail exactly what has been done.
  - In general, we don't need to see all the trials, errors and bug-fixes that went into this change, we only want to understand how it works now!
  - Try to ensure that the automated tests are working after all the commits in the set. This avoids other developers going back to an arbitrary earlier commit and finding that things don't work. There can be occasions when other problems cause test failures beyond our control, so we'll just have to remain alert to these and work around them as best we can.
- Where changes are likely to be more involved, or may change public APIs, authors should start a discussion with us first so that we can agree a good way forward.
- Before submitting a pull request, please ensure that all the automated tests are passing. They can be run using the `tools/run_tests` script. Please use `tools/run_tests --help` for more information.
- Any documentation should be updated accordingly. New examples and tests should be included wherever possible. Also consider making an entry in the change log.
- The author of the pull request needs to agree that they are donating the work to this project and to Raspberry Pi Ltd., so that we can continue to distribute it as open source to all our users. To indicate your agreement to this, we would ask that you finish commit messages with a blank line followed by `Signed-off-by: Your Name <your.email@your.domain>`.
- We'd like to conform to the common Python _PEP 8_ coding style wherever possible. To facilitate this we would recommend using our pre-commit hook, which can be installed by doing the following in the root of the repository:

```
pip3 install pre-commit
pre-commit install
```

This will install flake8 in a venv and will perform linting of changes prior to committing.

Thank you!
