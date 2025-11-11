# BoringCDN Welcome Content

Welcome content, example scripts, and templates for BoringCDN users.

## What is this?

This repository contains the default welcome content that new BoringCDN users receive when they sign up. It also includes comprehensive examples and templates to help you get started with BoringCDN.

## Contents

- **[index.html](index.html) & [style.css](style.css)** - BoringCDN user guide with upload examples

## Quick Start

When you sign up for BoringCDN, a "welcome" content item is automatically created with the files from this repository. You can:

1. View your welcome page immediately (check your dashboard for the URL)
2. Edit the files through the dashboard
3. Replace them with your own content
4. Use the API to automate deployments

## Uploading Files

Upload files to BoringCDN using the API with a tar.gz archive:

```bash
# Create archive from your build directory
tar -czf dist.tar.gz -C ./dist .

# Upload to BoringCDN
curl -X POST https://boringcdn.com/api/v1/upload \
  -H "Authorization: Bearer $BORINGCDN_TOKEN" \
  -F "file=@dist.tar.gz" \
  -F "content_id=$BORINGCDN_CONTENT_ID"

# Clean up
rm dist.tar.gz
```

### Getting Started

1. Create an API token at https://boringcdn.com/settings
2. Set your environment variables:
   ```bash
   export BORINGCDN_TOKEN="your-token-here"
   export BORINGCDN_CONTENT_ID="your-content-id"
   ```
3. Use the upload examples in [index.html](index.html)

**Important**: Only file uploads support API token authentication. Content management operations (create content, list content, delete content) must be done through the web dashboard.


## Contributing

Found a bug or have a suggestion? Contributions are welcome!

### Submitting Changes

1. **Fork the repository**
2. **Create a branch** (`git checkout -b feature/your-feature-name`)
3. **Make your changes** - Keep changes focused and test locally
4. **Commit** (`git commit -m "Brief description"`)
5. **Push and create a pull request**

### Contribution Ideas

- Improve the welcome page design or accessibility
- Enhance the upload script with better error handling
- Fix typos or improve documentation
- Add examples for other build systems or CI/CD platforms

### Guidelines

**Shell Scripts:**
- Use `set -e` for error handling
- Validate all inputs
- Provide helpful error messages

**HTML/CSS:**
- Use semantic HTML5 elements
- Mobile-first approach
- Maintain consistent indentation

Before submitting, test your changes locally and verify documentation is updated.

## License

MIT License - See [LICENSE](LICENSE) for details.

## Related

- [BoringCDN](https://github.com/tatehanawalt/boringcdn) - Main BoringCDN repository
- [Documentation](https://boringcdn.com/docs) - Full API documentation

## Questions?

- Create an issue in this repository
- Check the [BoringCDN documentation](https://boringcdn.com/docs)
- Visit [boringcdn.com](https://boringcdn.com)
