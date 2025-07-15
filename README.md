# npm-demo-changesets

[![NPM Package](https://img.shields.io/npm/v/npm-demo-changesets)](https://www.npmjs.com/package/npm-demo-changesets)

Demo library showcasing **Changesets** automation for NPM package publishing.

## Features

- ✅ Manual change declaration through changeset files
- ✅ Collaborative changelog creation with CLI workflow
- ✅ Flexible versioning control with developer input
- ✅ Feature branch publishing with custom NPM dist-tags
- ✅ Automatic cleanup of feature branch aliases

## Usage

```javascript
import { hello } from 'npm-demo-changesets';

console.log(hello('World')); // "Hello, World!"
```

## Changesets Workflow

### 1. Make Your Changes
Make code changes as needed for your feature or fix.

### 2. Create a Changeset
```bash
npm run changeset
```

This will prompt you to:
- Select the type of change (patch, minor, major)
- Write a summary of the change
- Generate a changeset file in `.changeset/`

### 3. Commit Everything
```bash
git add .
git commit -m "feat: add new feature with changeset"
git push
```

### 4. Release Process
1. Changesets action creates/updates a "Version Packages" PR
2. Review and merge the PR
3. Package is automatically published to NPM

## Feature Branches
Pushes to `feature/**` or `feat/**` branches publish pre-release versions with branch-specific NPM tags.

## Example Scenarios

1. **Add Feature**:
   ```bash
   # Make changes
   npm run changeset  # Select "minor", describe feature
   git add . && git commit -m "feat: add awesome feature"
   ```

2. **Fix Bug**:
   ```bash
   # Make changes
   npm run changeset  # Select "patch", describe fix
   git add . && git commit -m "fix: resolve issue"
   ```

3. **Breaking Change**:
   ```bash
   # Make changes
   npm run changeset  # Select "major", describe breaking change
   git add . && git commit -m "feat!: breaking API change"
   ```

## Changesets Commands

- `npm run changeset` - Create a new changeset
- `npm run version` - Apply changesets and update version
- `npm run release` - Publish to NPM

## Benefits of Changesets

- **Explicit**: Developers explicitly declare what changed
- **Collaborative**: Multiple people can contribute to changelogs
- **Flexible**: Full control over versioning decisions
- **Transparent**: Clear audit trail of what's being released

## Learn More

This demo repository is featured in the comprehensive guide: [**"The Ultimate Guide to NPM Release Automation: Semantic Release vs Release Please vs Changesets"**](https://oleksiipopov.com/blog/npm-release-automation/) - a detailed comparison of different NPM release automation tools with practical examples.
