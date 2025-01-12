## Telemetry in Aipa

At Aipa, we are dedicated to improving your experience and the overall quality of our software. To achieve this, we gather anonymous telemetry data which helps us understand how the tool is being used and identify areas for improvement.

### What We Collect

The telemetry data we collect includes:

- **Total Runtime**: The total time Aipa was active and running.
- **Command Runs**: How many commands were executed during a session.
- **Development Steps**: The number of development steps that were performed.
- **LLM Requests**: The number of LLM requests made.
- **User Inputs**: The number of times you provide input to the tool.
- **Operating System**: The operating system you are using (and Linux distro if applicable).
- **Python Version**: The version of Python you are using.
- **AIPA Version**: The version of Aipa you are using.
- **LLM Model**: LLM model(s) used for the session.
- **Time**: How long it took to generate a project.
- **Initial prompt**: App description used to create app (after Specification Writer Agent).
- **Architecture**: Architecture designed by Aipa for the app.
- **Documentation**: Aipa documentation that was used while creating the app.
- **User Email**: User email (if using Aipa VSCode Extgension, or if explicitly provided when running Aipa from the command line).
- **Aipa Tasks/Steps**: Information about the development tasks and steps Aipa does while coding the app.

All the data points are listed in [core.telemetry:Telemetry.clear_data()](../core/telemetry/__init__.py).

### How We Use This Data

We use this data to:

- Monitor the performance and reliability of Aipa.
- Understand usage patterns to guide our development and feature prioritization.
- Identify common workflows and improve the user experience.
- Ensure the scalability and efficiency of our language model interactions.

### Your Privacy

Your privacy is important to us. The data collected is purely for internal analysis and will not be shared with third parties. No personal information is collected, and telemetry data is completely anonymized. We adhere to best practices in data security to protect this information.

### Opting Out

We believe in transparency and control. If you prefer not to send telemetry data, you can opt-out at any time by setting `telemetry.enabled` to `false` in your `~/.aipa/config.json` configuration file.

After you update this setting, Aipa will no longer collect telemetry data from your machine.

### Questions and Feedback

If you have questions about our telemetry practices or would like to provide feedback, please open an issue in our repository, and we will be happy to engage with you.

Thank you for supporting Aipa and helping us make it better for everyone.
