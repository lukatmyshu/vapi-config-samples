# Vapi Configuration Samples

This repository contains sample configuration files for testing the Vapi Config Editor application. The files are organized by category and demonstrate various configuration patterns for the Vapi platform.

## Repository Structure

```
vapi-config-samples/
├── core-resources/          # Core Vapi resources
│   ├── *.assistant.json    # AI assistant configurations
│   ├── *.call.json         # Call configurations
│   ├── *.phone.json        # Phone number configurations
│   └── *.squad.json        # Squad (team) configurations
├── tools-integrations/      # Tool and integration configs
│   ├── *.tool.api.json     # API tool configurations
│   ├── *.tool.function.json # Function tool configurations
│   └── *.tool.sms.json     # SMS tool configurations
├── automation-workflows/    # Automation configurations
│   ├── *.workflow.json     # Workflow definitions
│   └── *.campaign.json     # Campaign configurations
├── data-knowledge/         # Data and knowledge base configs
│   ├── *.knowledge.json    # Knowledge base configurations
│   └── *.kb.json          # Alternative KB naming
├── templates/              # Template configurations
│   └── *.json             # Reusable config templates
└── edge-cases/            # Edge cases for testing
    └── *.json             # Invalid/malformed configs
```

## File Naming Conventions

The Config Editor uses file naming patterns to detect configuration types:

- **Assistants**: `*.assistant.json` or `assistant*.json`
- **Calls**: `*.call.json` or `call*.json`
- **Phone Numbers**: `*.phone.json` or `phone*.json`
- **Squads**: `*.squad.json` or `squad*.json`
- **Workflows**: `*.workflow.json` or `workflow*.json`
- **Campaigns**: `*.campaign.json` or `campaign*.json`
- **Knowledge Bases**: `*.knowledge.json` or `*.kb.json`
- **Tools**: `*.tool.{type}.json` (e.g., `*.tool.api.json`)

## Configuration Examples

### Assistant Configuration
Located in `core-resources/`, assistant configs define AI agents with:
- Model settings (provider, temperature, tokens)
- Voice configuration (provider, voice ID, settings)
- Tools and functions
- Behavioral settings

### Call Configuration
Call configs define outbound or inbound call settings:
- Phone number and assistant IDs
- Call metadata
- Recording settings
- Duration limits

### Tool Configurations
Tools extend assistant capabilities:
- **API Tools**: External API integrations
- **Function Tools**: Custom function definitions
- **SMS Tools**: Text messaging capabilities
- **Transfer Tools**: Call routing logic

### Workflow Configuration
Workflows define multi-step automations:
- Triggers (webhooks, schedules)
- Sequential or conditional steps
- Error handling
- Notifications

## Testing Scenarios

### 1. Basic Detection Test
- The editor should correctly categorize all files in their respective sections
- Files in `edge-cases/` should either fail validation or be ignored

### 2. Schema Validation Test
- Valid configs should pass schema validation
- `edge-cases/malformed-assistant.json` should show validation errors

### 3. Edit and Save Test
- Modify any configuration file
- Ensure changes are tracked as "dirty"
- Validate that schema checking works in real-time

### 4. Git Sync Test
- Create a feature branch
- Commit changes to a config file
- Create a pull request

## Environment Variables

When using these configs, you may need to replace placeholders:
- `${API_KEY}` - Your API authentication key
- `${TRIEVE_API_KEY}` - Trieve knowledge base API key
- `${CUSTOM_KB_API_KEY}` - Custom knowledge base API key

## Schema Information

All configurations follow the Vapi API schema available at:
https://api.vapi.ai/api-extended-json

The Config Editor will automatically load and validate against these schemas.

## Contributing

When adding new sample configurations:
1. Follow the naming conventions
2. Include all required fields per schema
3. Add realistic example data
4. Document any special features used

## License

These sample configurations are provided for testing purposes only.