# Custom Components

The custom components used for Home Assistant.

## Dahua

The Dahua integration is used to manage the Amcrest cameras.

The custom component comes from https://github.com/rroller/dahua and is added to this repository as a submodule. However, because the custom component contains other files as part of the repository, the submodule is initialized into the `dahua_dist` directory and a symbolic link is used to reference to subdirectory needed for Home Assistant to be able to reference this custom component.

