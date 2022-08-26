# Nitro build system for iOS

[![Step changelog](https://shields.io/github/v/release/underscopeio/bitrise-step-nitro-ios?include_prereleases&label=changelog&color=blueviolet)](https://github.com/underscopeio/bitrise-step-nitro-ios/releases)

Build React Native projects powered by Nitro


<details>
<summary>Description</summary>

This step allows you to easily run the Nitro builder by providing input parameters in a friendly way

</details>

## 🧩 Get started

Add this step directly to your workflow in the [Bitrise Workflow Editor](https://devcenter.bitrise.io/steps-and-workflows/steps-and-workflows-index/).

You can also run this step directly with [Bitrise CLI](https://github.com/bitrise-io/bitrise).

## ⚙️ Configuration

<details>
<summary>Inputs</summary>

| Key | Description | Flags | Default |
| --- | --- | --- | --- |
| `root_directory` | The directory within your project, in which your code is located. Leave this field empty if your code is not located in a subdirectory |  | `./` |
| `ios_scheme` | The name of the iOS scheme |  |  |
| `ios_xcconfig_path` | The path relative to project root directory where the custom `.xcconfig` file is located |  |  |
| `version_name` | The version name for the app |  |  |
| `version_code` | The version code for the app |  |  |
| `disable_version_name_from_package_json` | By default will get the 'version' field from package.json and set the version name |  | `no` |
| `disable_version_code_auto_generation` | By default will generate a timestamp based number and set the version code |  | `no` |
| `ios_certificate_url` | The url to download and install the certificate |  |  |
| `ios_certificate_passphrase` | Certificate passphrase | sensitive |  |
| `ios_codesigning_identity` | Codesigning identity |  |  |
| `ios_provisioning_profile_urls` | A string containing a '\|' separated values where provisioning profiles are located e.g. url1\|url2\|url3 |  |  |
| `ios_provisioning_profile_specifier` | The name of the provisioning profile when using a single one |  |  |
| `ios_team_id` | Specify the Team ID you want to use for the Apple Developer Portal |  |  |
| `ios_export_method` | The export method used to generate the IPA |  | `ad-hoc` |
| `cache_provider` | Choose the provider where cache artifacts will be persisted: - `fs`: File system - `s3`: Amazon - Simple Storage Service |  | `s3` |
| `disable_cache` | When setting this option to `yes` build cache optimizations won't be performed |  | `no` |
| `cache_env_var_lookup_keys` | A list of `\|` separated values with env variable keys to lookup to determine whether the build should be cached or not |  |  |
| `cache_file_lookup_paths` | A list of `\|` separated value paths (relative to the root of the repo or absolute) to lookup in order to determine whether the build should be cached or not |  |  |
| `disable_metro_cache` | Setting this field to yes will disable the React Native Metro cache feature |  | `no` |
| `pre_install_command` | Run command prior to install project dependencies (e.g. `rm -rf ./some-folder`) |  |  |
| `pre_build_command` | Run command prior to start building the app (e.g. `yarn tsc && yarn test`) |  |  |
| `post_build_command` | Run command once build successfully finished (e.g. `yarn publish`) |  |  |
| `output_directory` | The path to the directory where to place all of Nitro's output files |  | `$BITRISE_DEPLOY_DIR` |
| `entry_file` | The entry file for bundle generation |  | `$ENTRY_FILE` |
| `debug` | Enable verbose logs |  | `no` |
| `fail_safe` | Runing the app in this mode allows you to prevent the build to fail but you can check the status in further steps |  |  |
</details>

<details>
<summary>Outputs</summary>

| Environment Variable | Description |
| --- | --- |
| `NITRO_BUILD_STATUS` | The status of the latest build (success / failure) |
| `NITRO_OUTPUT_DIR` | The path to the directory where to place all of Nitro's output files |
| `NITRO_LOGS_PATH` | The full path to access the build log |
| `NITRO_DEPLOY_PATH` | The full path to access the build artifacts |
| `NITRO_SUMMARY_PATH` | The full path to access the build summary report |
</details>

## 🙋 Contributing

We welcome [pull requests](https://github.com/underscopeio/bitrise-step-nitro-ios/pulls) and [issues](https://github.com/underscopeio/bitrise-step-nitro-ios/issues) against this repository.

For pull requests, work on your changes in a forked repository and use the Bitrise CLI to [run step tests locally](https://devcenter.bitrise.io/bitrise-cli/run-your-first-build/).

Learn more about developing steps:

- [Create your own step](https://devcenter.bitrise.io/contributors/create-your-own-step/)
- [Testing your Step](https://devcenter.bitrise.io/contributors/testing-and-versioning-your-steps/)
