# Novel Writer Multi-Agent System

A novel creation platform based on multi-agent collaboration, completing the entire creative process from idea to finished manuscript through the collaborative work of four specialized agents.

## Features

### Multi-Agent Collaboration
- **Inspirer**: Creative divergence, expanding user input into rich creative materials
- **Architect**: Structure design, transforming inspiration into outlines and chapter details
- **Writer**: Content creation, completing chapter writing based on detailed outlines
- **Polisher**: Language optimization, enhancing the literary quality and humanization of content

### Novel Type Support
- **Short stories** (1-10 chapters): Single workflow completion
- **Novellas** (11-30 chapters): Batch planning
- **Long serials** (30+ chapters): Group management, 10 chapters per group

### Progress Management
- Automatic creation progress recording
- Support for continuing interrupted writing
- Long serials managed in groups of 10 chapters

### Style Management
- Multiple preset styles (default, romance, mystery, historical, fantasy)
- Support for custom styles
- Unified style throughout the book

## Quick Start

### Start Creating
1. Tell the system your creative needs (theme, keywords, emotional tone, etc.)
2. The system automatically activates the Inspirer
3. Complete the creation following the workflow

### Continue Writing
1. Tell the system to continue writing your work
2. The system reads `WORKSPACE/CURRENT.MD`
3. Automatically continues writing

### Change Style
1. Specify the style type (e.g., use mystery style)
2. The system applies the corresponding style
3. Re-polish related content

## Directory Structure

```
novel-writer/
├── AGENTS.MD              # Main workflow file
├── AGENTS/                # Agent definitions
│   ├── Inspirer.MD       # Inspirer
│   ├── Architect.MD      # Architect
│   ├── Writer.MD         # Writer
│   └── Polisher.MD       # Polisher
├── SKILLS/                # Skill definitions
│   ├── Creative_Divergence.MD  # Creative divergence skill
│   └── Structure_Design.MD     # Structure design skill
├── STYLES/                # Style definitions
│   ├── Default_Style.MD  # Default style
│   ├── Romance_Style.MD  # Romance style
│   ├── Mystery_Style.MD  # Mystery style
│   ├── Historical_Style.MD # Historical style
│   └── Fantasy_Style.MD  # Fantasy style
└── WORKSPACE/             # Workspace
    ├── CURRENT.MD         # Current progress (global)
    └── [Book Name]/       # Project folder
        ├── AGENT/         # Agent outputs
        │   └── Inspirer.md
        ├── CONTENT/       # Chapter content (final version)
        │   ├── chapter_1.md
        │   └── ...
        ├── OUTLINE/       # Full outline
        │   └── outline.md
        ├── DETAILED_OUTLINE/ # Chapter detailed outlines
        │   ├── chapter_1.md
        │   └── ...
        └── CURRENT_PROCESS/ # Current progress
            └── current.md
```

## Usage Examples

### Example 1: Start Creating a New Novel
```
User: I want to write an urban romance novel with the theme "missed encounters and reunions" and a warm, healing emotional tone
System: Activating Inspirer for creative divergence...
System: Activating Architect to design full outline and chapter details...
System: Activating Writer to start writing Chapter 1...
System: Activating Polisher to optimize language expression...
```

### Example 2: Continue an Unfinished Work
```
User: Please continue writing my novel "Urban Romance"
System: Reading WORKSPACE/CURRENT.MD...
System: Reading the last 2 chapters...
System: Reading the next chapter outline...
System: Continuing to write Chapter X based on context...
```

### Example 3: Change Writing Style
```
User: Please re-polish Chapter 3 using mystery style
System: Reading STYLES/Mystery_Style.MD...
System: Applying mystery style for polishing...
System: Outputting polished version...
```

## Workflow

### Complete Creation Workflow
```
User Input → Inspirer → Architect → Writer → Polisher → Final Output
```

### Long Serial Workflow
```
Chapters 1-10 creation → Record progress → Chapters 11-20 creation → Record progress → ...
```

### Continuing Writing Workflow
```
Read progress → Read last 2 chapters → Read outline → Continue writing
```

## Notes

1. **Long serials**: Recommend managing in groups of 10 chapters, recording progress after completing each group
2. **Before continuing**: Always read the last 2 chapters to ensure plot continuity
3. **Style consistency**: Maintain consistent style throughout the book, avoid style confusion
4. **Character consistency**: Pay attention to character personality and language consistency
5. **Plot continuity**: Maintain plot logic and coherence

## Technical Support

For questions or suggestions, please contact:
- Submit an Issue
- Send email to the project maintainer

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details