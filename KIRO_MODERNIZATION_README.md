# Kiro Modernization Request - Quick Start Guide

## Overview

This repository contains scripts and documentation to help you request a comprehensive modernization plan from **Kiro** (or any LLM) for migrating the Bob's Used Bookstore Classic application from **.NET Framework 4.8** to **.NET 9.0**.

## Files Included

### 📋 Documentation
- **`kiro-modernization-plan.md`** - Complete 7-phase modernization plan with:
  - Detailed objectives for each phase
  - Specific Kiro commands to execute
  - Code transformation examples
  - Success metrics and checklists
  - Rollback procedures

### 🛠️ Scripts

#### PowerShell (Windows)
```bash
.\kiro-modernization-request.ps1
```

**Features:**
- Interactive menu system
- Color-coded output
- Phase-by-phase execution
- Automatic report generation
- Kiro installation detection

#### Bash (Linux/macOS)
```bash
chmod +x kiro-modernization-request.sh
./kiro-modernization-request.sh
```

**Features:**
- POSIX-compliant shell script
- Same functionality as PowerShell version
- Works on Linux, macOS, WSL

## Quick Start

### Option 1: Interactive Mode

#### Windows (PowerShell)
```powershell
# Run the interactive script
.\kiro-modernization-request.ps1

# Or with specific phase
.\kiro-modernization-request.ps1 -Phase analysis
```

#### Linux/macOS (Bash)
```bash
./kiro-modernization-request.sh

# Or with verbose output
VERBOSE=1 ./kiro-modernization-request.sh
```

### Option 2: Request from LLM Directly

1. **Copy the context** from the script output:
   ```
   KIRO MODERNIZATION PLAN REQUEST
   ================================
   
   Project: brunosilvaJava/bobs-used-bookstore-classic
   ...
   ```

2. **Submit to your LLM/IDE**:
   ```
   "Please provide a modernization plan for Bob's Used Bookstore Classic
    using the attached context and Kiro commands."
   ```

3. **Get back**: A detailed modernization plan with Kiro commands

## Menu Options

### Main Menu
1. **Analyze Project with Kiro**
   - Generates comprehensive analysis report
   - Identifies compatibility issues
   - Creates patterns analysis
   - Outputs: `kiro-reports/`

2. **Request Modernization Plan**
   - Prepares LLM request context
   - Saves request to file
   - Shows next steps

3. **View Migration Phases**
   - Interactive phase selection
   - Displays phase-specific commands
   - Option to execute all phases

4. **Check Kiro Installation**
   - Verifies Kiro is installed
   - Shows version information
   - Provides installation instructions

5. **View Full Plan Documentation**
   - Displays modernization plan
   - Shows code examples
   - Lists transformations

6. **Generate Sample Commands**
   - Shows all Kiro commands
   - Ready to copy/paste

## Output Structure

Generated reports are saved in `kiro-reports/` directory:

```
kiro-reports/
├── analysis_2026-04-27_14-30-45.json
├── readiness_2026-04-27_14-30-45.html
├── patterns_2026-04-27_14-30-45.json
└── llm-request-context_2026-04-27_14-30-45.txt
```

## Kiro Commands Reference

### Analysis Phase
```bash
kiro analyze \
  --input . \
  --type "asp-net-framework" \
  --target-framework "net9.0" \
  --output analysis-report.json \
  --include-dependencies \
  --include-breaking-changes
```

### Project Conversion
```bash
kiro convert-project \
  --input app/Bookstore.Web/Bookstore.Web.csproj \
  --target-framework net9.0 \
  --mvc-to-core
```

### Database Migration (EF6 → EF Core)
```bash
kiro convert-ef6-to-core \
  --input app/Bookstore.Data/ApplicationDbContext.cs \
  --target-version 8.0 \
  --apply-fluent-api
```

### Code Modernization
```bash
kiro modernize-csharp \
  --input . \
  --target csharp-9.0 \
  --patterns "nullable-reference-types,records,top-level-statements"
```

### Testing & Validation
```bash
kiro validate-migration \
  --project . \
  --old-version net48 \
  --new-version net9.0 \
  --report migration-quality.html
```

### Generate Documentation
```bash
kiro document-migration \
  --project . \
  --old-version net48 \
  --new-version net9.0 \
  --output MIGRATION_GUIDE.md
```

## Installation Requirements

### Kiro IDE
Required for executing actual Kiro commands:

```bash
# Install globally via npm
npm install -g kiro-ide

# Or download from
https://kiro-ide.dev/download
```

### Scripts
No additional requirements for running the scripts:
- **PowerShell**: Built into Windows, available on Linux/macOS
- **Bash**: Standard on Linux/macOS, available on Windows via WSL

## 7-Phase Modernization Plan

### Phase 1: Analysis & Planning (2-3 days)
- Analyze current codebase using Kiro
- Identify compatibility issues
- Generate migration roadmap

### Phase 2: Project Structure Conversion (3-5 days)
- Create new .NET 9 projects
- Migrate domain model first
- Update build system

### Phase 3: Code Transformation (5-7 days)
- Transform C# code to modern patterns
- Convert configuration (web.config → appsettings.json)
- Update middleware (OWIN → ASP.NET Core)

### Phase 4: Dependency Updates (2-3 days)
- Update NuGet packages
- Remove obsolete dependencies
- Add required .NET Core packages

### Phase 5: Database & ORM Migration (3-4 days)
- Convert EF6 to EF Core 8
- Update DbContext configurations
- Create and test migrations

### Phase 6: Testing & Validation (4-5 days)
- Unit test conversion
- Integration testing
- Performance benchmarking

### Phase 7: Documentation & Deployment (2-3 days)
- Create migration documentation
- Prepare Docker build
- Setup CI/CD pipelines

## Example Usage

### Windows PowerShell
```powershell
# Start interactive planning tool
.\kiro-modernization-request.ps1

# Select "Analyze Project with Kiro"
# Follow prompts to generate reports
# Reports saved to kiro-reports/ directory
```

### Linux/macOS Bash
```bash
# Make script executable (first time only)
chmod +x kiro-modernization-request.sh

# Start interactive planning tool
./kiro-modernization-request.sh

# Select "Analyze Project with Kiro"
# Follow prompts to generate reports
# Reports saved to kiro-reports/ directory
```

### Non-Interactive Execution (PowerShell)
```powershell
.\kiro-modernization-request.ps1 -NonInteractive -Phase analysis
```

### Non-Interactive Execution (Bash)
```bash
VERBOSE=1 ./kiro-modernization-request.sh
```

## Key Information

### Project Details
- **Repository**: brunosilvaJava/bobs-used-bookstore-classic
- **Current Framework**: .NET Framework 4.8
- **Target Framework**: .NET 9.0 LTS
- **Main Components**:
  - Bookstore.Web (ASP.NET MVC)
  - Bookstore.Data (Entity Framework 6)
  - Bookstore.Domain (Business Logic)
  - Bookstore.Common (Shared Utilities)
  - Bookstore.Cdk (AWS Infrastructure)

### Language Composition
- JavaScript: 60.9%
- C#: 17.5%
- CSS: 13.7%
- HTML: 7.6%
- Dockerfile: 0.2%
- PowerShell: 0.1%

## Success Metrics

Target improvements after modernization:

| Metric | Target |
|--------|--------|
| Test Coverage | >85% |
| Build Time | <2 min |
| Application Size | <50MB |
| Startup Time | <5s |
| Memory Usage | <200MB |
| API Response Time | <200ms |

## Troubleshooting

### Kiro Not Found
```powershell
# PowerShell
npm install -g kiro-ide

# Or bash
npm install -g kiro-ide
```

### Permission Denied (Bash)
```bash
chmod +x kiro-modernization-request.sh
./kiro-modernization-request.sh
```

### Reports Not Generated
- Ensure `kiro-reports/` directory is writable
- Check Kiro installation: `kiro --version`
- Verify project structure is correct

## Support & Resources

- **Kiro Documentation**: https://kiro-docs.dev
- **ASP.NET Core Migration**: https://docs.microsoft.com/en-us/dotnet/core/porting/
- **EF6 to EF Core**: https://docs.microsoft.com/en-us/ef/efcore-and-ef6/
- **AWS SDK for .NET**: https://aws.amazon.com/sdk-for-net/

## Next Steps

1. **Run the script** to generate your modernization plan
2. **Review the plan** in `kiro-modernization-plan.md`
3. **Start with Phase 1** - Analysis
4. **Execute phases sequentially**
5. **Track progress** with generated reports
6. **Deploy** once all phases are complete

## Contributing

To improve these scripts:
1. Test on your platform (Windows/Linux/macOS)
2. Report issues or enhancements
3. Submit pull requests with improvements

## License

This project is licensed under the MIT License - see LICENSE file for details.

---

**Last Updated**: 2026-04-27  
**Version**: 1.0  
**Status**: Ready for use
