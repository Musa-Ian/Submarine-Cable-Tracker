# 🌊 Submarine Cable Tracker

An interactive web application that visualizes the world's submarine internet cables using Mapbox and real-time data from TeleGeography's submarine cable database.

![Submarine Cable Tracker](https://via.placeholder.com/800x400/0a0a0a/00d4ff?text=Submarine+Cable+Tracker)

## Features

- **Real-time Cable Data** - Live submarine cable routes from TeleGeography API
- **Interactive Map** - Click cables for detailed information
- **Country Analysis** - Find possible cables between any two countries
- **Network Simulation** - Simulated traceroute showing how data travels
- **Landing Points** - Toggle cable landing stations worldwide
- **Responsive Design** - Works on desktop and mobile devices

## Live Demo

🚀 **[View Live Demo](https://submarine-cable-tracker.vercel.app)**

## Local Development

1. Clone this repository
2. Open `index.html` in your browser
3. Enter your Mapbox token or use the pre-filled one

## Vercel Deployment

### Quick Deploy

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https%3A%2F%2Fgithub.com%2Fyourusername%2Fsubmarine-cable-tracker)

### Manual Deployment

1. **Install Vercel CLI**:
   ```bash
   npm i -g vercel
   ```

2. **Login to Vercel**:
   ```bash
   vercel login
   ```

3. **Deploy**:
   ```bash
   vercel --prod
   ```

4. **Set Environment Variable**:
   - Go to your Vercel dashboard
   - Navigate to your project settings
   - Add environment variable:
     - Name: `MAPBOX_TOKEN`
     - Value: `your_mapbox_token_here`

## Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| `MAPBOX_TOKEN` | Your Mapbox public access token | Yes |

## Getting a Mapbox Token

1. Go to [Mapbox Account](https://account.mapbox.com/access-tokens/)
2. Create a free account
3. Copy your default public token (starts with `pk.`)
4. Use it in your deployment

## API Dependencies

- **Mapbox GL JS** - Map rendering and interactions
- **TeleGeography Submarine Cable Map API** - Real cable data
  - Cables: `https://www.submarinecablemap.com/api/v3/cable/cable-geo.json`
  - Landing Points: `https://www.submarinecablemap.com/api/v3/landing-point/landing-point-geo.json`

## How It Works

### Data Sources
- **Cable Routes**: Real submarine cable paths from TeleGeography
- **Landing Points**: Physical locations where cables come ashore
- **Country Analysis**: Matches countries to likely cable routes

### Network Tracing
The app simulates network tracing to show how your internet data might travel:
1. Local network → ISP
2. ISP core network
3. Submarine cable entry point
4. Undersea cable transmission
5. Destination cable landing
6. Destination network

## Technologies Used

- **Frontend**: Vanilla JavaScript, HTML5, CSS3
- **Mapping**: Mapbox GL JS
- **Deployment**: Vercel
- **Data**: TeleGeography Submarine Cable Map API

## Browser Support

- Chrome/Chromium 57+
- Firefox 53+
- Safari 11+
- Edge 79+

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

MIT License - see [LICENSE](LICENSE) for details.

## Acknowledgments

- [TeleGeography](https://www.submarinecablemap.com/) for submarine cable data
- [Mapbox](https://www.mapbox.com/) for mapping platform
- [Vercel](https://vercel.com/) for hosting platform

## Support

For issues or questions:
- Create an issue in this repository
- Check the [Mapbox documentation](https://docs.mapbox.com/)
- Review [TeleGeography's API documentation](https://www.submarinecablemap.com/api/)