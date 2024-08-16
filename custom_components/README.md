# Custom Components

The custom components used for Home Assistant. They're provided as Git submodules, cloned to this directory with the added suffix `_dist`, and provided to Home Assistant via a symbolic link. The added complexity with the directory naming is because the third-party repositories contain other files at their root aside from the custom component. So in order for Home Assistant to recognize these subdirectories as custom components, the only files that can reside within them must be those that directly make the custom component.

## Dahua

https://github.com/rroller/dahua

The Dahua integration is used to manage the Amcrest cameras.

