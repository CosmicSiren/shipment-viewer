# Shipment Data Viewer - GitHub Pages Edition

An enhanced web-based shipment tracking and analysis tool that provides comprehensive visualization of shipment data. This application is optimized for GitHub Pages deployment and features efficient data chunking for handling large datasets.

## Features

### Core Functionality
- **Shipment Navigation**: Browse through 1,571 shipments with previous/next navigation
- **Smart Search**: Quickly find specific shipments by ID across all data chunks
- **Efficient Data Loading**: Data is split into 32 chunks (50 shipments each) for optimal performance
- **Real-time Updates**: Dynamic loading of data chunks as you navigate

### Data Visualization
- **Quick Stats Dashboard**: 
  - Total log entries per shipment
  - Duration in days
  - Key milestones count
  - Associated documents
- **Detailed Overview Cards**:
  - Basic shipment information (ID, booking reference, container details)
  - Route information (origin/destination ports, ETD/ETA)
- **Interactive Timeline**: Visual representation of shipment events and milestones
- **Raw Data Access**: View and copy complete JSON data for each shipment

### Technical Features
- **Zero Dependencies**: Pure HTML, CSS, and JavaScript - no external libraries required
- **Responsive Design**: Works seamlessly on desktop and mobile devices
- **Offline Capable**: Once loaded, data chunks are cached for faster access
- **GitHub Pages Ready**: Static site architecture perfect for GitHub Pages hosting

## Project Structure

```
github-pages/
├── index.html          # Main application file with embedded CSS and JavaScript
├── data_index.json     # Index file containing metadata about data chunks
├── data/              # Directory containing chunked shipment data
│   ├── chunk_0.json   # First 50 shipments
│   ├── chunk_1.json   # Next 50 shipments
│   └── ...            # Up to chunk_31.json
└── README.md          # This file
```

## Data Format

### Index File (data_index.json)
```json
{
  "total_shipments": 1571,
  "chunks_per_file": 50,
  "total_chunks": 32,
  "chunks": [
    {
      "id": 0,
      "filename": "data/chunk_0.json",
      "start_index": 0,
      "end_index": 50,
      "count": 50
    }
    // ... more chunks
  ]
}
```

### Chunk Files (data/chunk_*.json)
Each chunk file contains shipment data in the following format:
```json
{
  "shipment_id": {
    "logs": [
      {
        "timestamp": "2024-01-01T00:00:00Z",
        "entity_type": "Shipment",
        "entity_id": "unique_id",
        "change_reason": "Created",
        "new_value": { /* shipment details */ }
      }
    ],
    "unique_entity_count": 5
  }
}
```

## Usage

1. **Local Development**: 
   - Open `index.html` directly in a web browser
   - No server setup required

2. **GitHub Pages Deployment**:
   - Push all files to a GitHub repository
   - Enable GitHub Pages in repository settings
   - Access via `https://[username].github.io/[repository-name]/`

3. **Navigation**:
   - Use Previous/Next buttons to browse shipments sequentially
   - Enter a shipment ID in the search box to jump directly to it
   - View chunk information to see which data file is currently loaded

## Performance Optimization

- **Lazy Loading**: Only loads data chunks when needed
- **Chunk Caching**: Previously loaded chunks remain in memory
- **Efficient Search**: Searches through chunks sequentially until match is found
- **Minimal DOM Updates**: Only updates changed content when navigating

## Browser Compatibility

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Future Enhancements

- Export functionality for filtered data
- Advanced search with multiple criteria
- Data visualization charts
- Bookmark/favorite shipments
- Print-friendly views

## License

This project is designed for internal use and shipment tracking purposes.

---

Built with simplicity and performance in mind for efficient shipment data analysis.