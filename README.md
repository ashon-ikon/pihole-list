# Pi-hole Ad Lists

This repository provides curated, categorized ad-blocking lists for Pi-hole to enhance privacy and reduce unwanted content. Our goal is to create comprehensive, well-organized blocklists that target specific categories of domains while maintaining usability and performance.

## Purpose

- **Privacy Protection**: Block tracking, analytics, and data collection domains
- **Content Filtering**: Organize lists by content type for granular control
- **Performance**: Curated lists to avoid over-blocking legitimate functionality
- **Maintenance**: Regularly updated and community-driven blocklists

## Directory Structure

```
├── socials/          # Social media platforms
│   ├── youtube.txt
│   ├── facebook.txt
│   ├── tiktok.txt
│   └── instagram.txt
├── adult/            # Adult content sites
│   └── adult-sites.txt
└── README.md
```

## File Format

All list files follow the `/etc/hosts` canonical format:
```
0.0.0.0 example.com
0.0.0.0 www.example.com
```

## Usage

### Adding Lists to Pi-hole
1. Go to Pi-hole Admin Panel → Group Management → Adlists
2. Add the raw GitHub URL for each list you want to use:
   ```
   https://raw.githubusercontent.com/[username]/[repo]/main/socials/youtube.txt
   https://raw.githubusercontent.com/[username]/[repo]/main/socials/facebook.txt
   ```
3. Update gravity: `pihole -g`

### Selective Blocking
Choose only the categories you need:
- Use individual files for targeted blocking
- Combine multiple categories as needed
- Test with small lists before deploying larger ones

## Categories

### Socials
Contains lists for major social media platforms:
- **youtube.txt** - YouTube domains
- **facebook.txt** - Facebook/Meta domains  
- **tiktok.txt** - TikTok domains
- **instagram.txt** - Instagram domains

### Adult
Contains lists for adult content sites:
- **adult-sites.txt** - Adult content domains

## Contributing

We welcome contributions to improve and expand these lists!

### Adding Domains
1. Use the format: `0.0.0.0 domain.com`
2. Include both www and non-www variants when applicable
3. Sort domains alphabetically within each file
4. One domain per line
5. Add comments to explain the purpose of domains when helpful

### Domain Discovery
- Use web crawling tools to discover related domains
- Analyze network traffic to identify tracking domains
- Research domain relationships and subdomains
- Verify domains serve ads/tracking before adding

### Guidelines
- Test changes before submitting pull requests
- Ensure domains actually serve unwanted content
- Avoid blocking essential functionality
- Document the source/reason for adding domains
