# System Template

A blueprint for my personal system configuration.

## Rules and Guidelines

### State the Obvious:
Structure and intent should be explicitly stated for personal use and the use of AI assistants.

### Organization
- Files in 'shared' will be universally applicable. They may have conditional logic for different implementations within them. Shared rules are preferred when practical.

- Files in mac or linux are universall to that machine. Files within user folders are specific to that user in that machine.

- Machines or users may have an index.md file with info such as IP address or other general reference

### Key Concepts
- Use git to keep this synced between devices. Use github for syncing through the private repo https://github.com/BenMiriello/system-template


### Style Guide
- Both human and machine authors and editors should keep rules succinct and clear. Do not repeat rules that can reasonably be aggregated.

- Instructions to AI models will be stated in depth elsewhere, however as a global rule the AI should not edit or add files it was not explicitly asked or permitted to edit. This is true at all times unless otherwise explicitly stated in the system prompt or user prompt. Suggestions for edits can be made and executed upon granted permission.

- Leaving dates for the time any piece of information was written is discouraged and git logs should be used instead. Timestamps can become more confusing than helpful if they are not manually updated later. Leave them only when necessary.

## Scope
Concepts covered include:
- Storage scheme
- System config files

## Roadmap
To be included:
- samba and file sharing config
- ufw config
- driver install steps and config (especially cuda, torch, transformers) for linux
- background process scripts and config
- scripts to rebuild systems from scratch
- Local AI integration
- 
- General implementation instructions for custom apps such as
    - note taking
    - local LLM interface
    - control panel
    - other
