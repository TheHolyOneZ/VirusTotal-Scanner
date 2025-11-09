# VirusTotal-Scanner
This extension adds powerful file scanning capabilities to your Discord bot using VirusTotal's database of 70+ antivirus engines. Users can upload files directly in Discord and get comprehensive malware analysis reports instantly.
> 💡 **Built for the Zygnal Ecosystem — to download and use this extension, you must be part of the Zygnal Ecosystem.**  
> This extension (cog) is part of the **Zygnal Ecosystem** and is only available through its supported platforms.  
> You can use it with:  
> - The **[Discord Bot Framework](https://github.com/TheHolyOneZ/discord-bot-framework)** — ideal for developers who want full control and flexibility *(includes an integrated extension marketplace)*, or  
> - The **[ZygnalBot](https://zygnalbot.de)** — a prebuilt, plug-and-play Discord bot *(also includes an integrated extension marketplace)*.  
>
> Browse and install extensions at [zygnalbot.com/extension](https://zygnalbot.com/extension).  
> For help or community discussions, join us on Discord: [discord.gg/sgZnXca5ts](https://discord.gg/sgZnXca5ts)
# VirusTotal Scanner Documentation

## What is this extension?

This extension adds powerful file scanning capabilities to your Discord bot using VirusTotal's database of 70+ antivirus engines. Users can upload files directly in Discord and get comprehensive malware analysis reports instantly.

## Main Features

### File Scanning
- Upload any file type directly in Discord
- Scan files up to 32MB in size
- Get results from 70+ antivirus engines
- Detailed threat analysis and reporting
- Real-time scanning with progress updates

### Interactive Interface
- Easy-to-use buttons for file upload
- Detailed scan results with threat breakdown
- Scan history tracking for all users
- Filter and search through past scans
- One-click access to detailed reports

### Security & Control
- Rate limiting to prevent spam
- Role-based access control
- Channel restrictions for scanning
- Admin panel for full configuration
- Automatic threat alerts for dangerous files

### Advanced Features
- Auto-scanning in designated channels
- Webhook notifications for threats
- Data export in JSON/CSV formats
- Comprehensive scan history
- Global management for bot owners

## Available Commands

### User Commands
- `!vtscan` - Opens the main scanner interface with upload button
- `!vtstats` - View your personal scanning statistics
- `!vtscan status` - Check current scanner configuration and limits

### Admin Commands
- `!vtadmin` - Opens the admin control panel
- `!vtadmin panel` - Interactive admin interface with buttons
- `!vtadmin toggle` - Enable/disable the scanner
- `!vtadmin setapi <key>` - Set your VirusTotal API key
- `!vtadmin config` - View detailed configuration
- `!vtadmin stats` - Server-wide scanning statistics

### Configuration Commands
- `!vtadmin autoscan add/remove <channel>` - Set up automatic scanning
- `!vtadmin alerts <channel>` - Configure threat alert notifications
- `!vtadmin export json/csv` - Export scan data
- `!vtadmin ratelimit <number> <minutes>` - Set scanning limits
- `!vtadmin cleanup <days>` - Remove old scan records

### Global Commands (Bot Owner Only)
- `!vtglobal` - Global scanner management
- `!vtglobal toggle` - Enable/disable globally
- `!vtglobal stats` - Cross-server statistics
- `!vtglobal cleanup <days>` - Global data cleanup

## How to Set Up

### 1. Get VirusTotal API Key
- Go to https://www.virustotal.com/gui/join-us
- Create a free account
- Get your API key from your profile

### 2. Configure the Scanner
- Use `!vtadmin setapi <your_api_key>` to set up scanning
- Use `!vtadmin toggle` to enable the scanner
- Set up rate limits with `!vtadmin ratelimit 5 60` (5 scans per hour)

### 3. Set Permissions (Optional)
- Add roles that can use the scanner
- Restrict to specific channels
- Configure auto-scanning channels

## Scanner Interface

### Main Panel Buttons
When users type `!vtscan`, they get an interface with:

- **📤 Upload & Scan File** - Upload a file for scanning
- **📋 View Scan History** - See all your previous scans
- **ℹ️ Scanner Info** - View scanner status and limits

### Scan Results Buttons
After scanning, users can:

- **📊 Detailed Results** - View comprehensive threat breakdown
- **🔍 View All Scans** - Browse complete scan history
- **🗑️ Delete Results** - Remove scan results

### Admin Panel Buttons
Administrators get additional controls:

- **🛑 Toggle Scanner** - Enable/disable system
- **👥 Manage Roles** - Control who can scan files
- **🔑 Set API Key** - Configure VirusTotal access
- **📊 View All Scans** - See server-wide scan history
- **⚙️ Advanced Settings** - Rate limits, auto-scan, alerts

## Scan Results Explained

### Threat Levels
- **🟢 Clean** - No threats detected by any engine
- **🟡 Suspicious** - Flagged as potentially unwanted by some engines
- **🔴 Malicious** - Confirmed malware detected by multiple engines

### Result Details
- **Detection Count** - How many engines flagged the file (e.g., 3/70)
- **Engine Names** - Which specific antivirus programs detected threats
- **Threat Names** - What type of malware was identified
- **File Hash** - Unique identifier for the scanned file
- **Scan Date** - When the analysis was performed

### History Features
- **Personal History** - View all your scanned files
- **Filtering** - Search by filename or threat status
- **Pagination** - Browse through multiple pages of results
- **Export Options** - Download scan data for records

## Auto-Scanning Feature

### What it does
- Automatically scans files uploaded to designated channels
- No user interaction required
- Immediate threat detection and alerts
- Perfect for file sharing channels

### Setup
1. Use `!vtadmin autoscan add #channel-name`
2. Files uploaded to that channel are scanned automatically
3. Results posted immediately with threat warnings
4. Alerts sent to configured notification channel

## Threat Alerts

### Alert System
- Automatic notifications when malicious files are detected
- Sent to designated alert channel
- Includes file details, user info, and threat summary
- Helps moderators respond quickly to security threats

### Configuration
- Use `!vtadmin alerts #alert-channel` to set up
- Alerts trigger for malicious and suspicious files
- Can be enabled/disabled per server
- Includes threat severity and detection details

## Rate Limiting

### Why it exists
- Prevents API quota exhaustion
- Stops spam and abuse
- Ensures fair usage for all users
- Protects against accidental overuse

### Default Limits
- 5 scans per user per hour
- 32MB maximum file size
- Configurable by administrators
- Separate limits per server

### Customization
- `!vtadmin ratelimit 10 30` - 10 scans per 30 minutes
- `!vtglobal setsize 64` - Increase max file size to 64MB
- Limits apply per user, not per server
- Resets automatically after time window

## Data Management

### Scan History
- All scans stored with timestamps
- User information and file details
- Complete threat analysis results
- Searchable and filterable

### Export Options
- **JSON Format** - Complete data with all details
- **CSV Format** - Spreadsheet-friendly summary
- **Admin Export** - All server scans
- **User Export** - Personal scan history only

### Cleanup Tools
- Remove scans older than specified days
- Server-specific or global cleanup
- Automatic cleanup options
- Preserves important threat data

## Security & Privacy

### Data Handling
- Files sent to VirusTotal for analysis
- No files stored locally on your server
- Scan results cached for history
- User data protected and encrypted

### Access Control
- Role-based permissions
- Channel restrictions available
- Admin-only configuration
- Rate limiting prevents abuse

### API Security
- API keys encrypted in storage
- Automatic key validation
- Secure communication with VirusTotal
- Error handling for failed requests

## Common Use Cases

### Server Security
- Scan suspicious files before allowing downloads
- Monitor file uploads in public channels
- Alert staff to potential threats immediately
- Maintain security logs for compliance

### Community Safety
- Let users verify files before sharing
- Provide peace of mind for file exchanges
- Educational tool about cybersecurity
- Build trust in your community

### Moderation Tool
- Quick threat assessment for reported files
- Evidence collection for security incidents
- Automated threat response
- Comprehensive audit trails

## Troubleshooting

### Common Issues

**Scanner not working:**
- Check if API key is set correctly
- Verify scanner is enabled with `!vtadmin`
- Ensure user has permission to scan
- Check rate limits haven't been exceeded

**"API key not configured" error:**
- Use `!vtadmin setapi <key>` to set your VirusTotal API key
- Make sure the key is exactly 64 characters
- Verify the key is active on VirusTotal website

**Rate limit exceeded:**
- Wait for the time window to reset
- Administrators can adjust limits with `!vtadmin ratelimit`
- Check current limits with `!vtscan status`

**File too large:**
- Default limit is 32MB
- Bot owners can increase with `!vtglobal setsize`
- Consider compressing large files

### Getting Help
- Use `!vtscan status` to check configuration
- Use `!vtadmin config` for detailed settings
- Check the scanner info panel for current limits
- Contact administrators if issues persist

## Best Practices

### For Administrators
- Set reasonable rate limits to prevent abuse
- Configure auto-scanning for high-risk channels
- Set up threat alerts for quick response
- Regularly review scan statistics
- Keep API quotas in mind when setting limits

### For Users
- Scan suspicious files before opening
- Check scan history for patterns
- Report false positives to administrators
- Don't rely solely on automated scanning
- Use common sense with file safety

This scanner provides enterprise-level file security analysis directly in your Discord server, making it easy to maintain a safe environment for your community.
