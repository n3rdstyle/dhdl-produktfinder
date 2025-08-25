# DHDL Produktfinder - Clean V2

## Overview
This is a clean, production-ready version of the DHDL (Die Höhle der Löwen) Product Finder application with all dependencies optimized and problematic components removed.

## Key Features
- **Multimodal Search**: Text and image search capabilities
- **Local Keyword Search**: Fast German keyword search with fuzzy matching
- **Enhanced Tags**: Comprehensive German tag generation for better search results
- **Staffel 18 Focus**: Filtered to show only current season products
- **Mobile Responsive**: Optimized for mobile and tablet devices
- **Brand Integration**: Automatic brand prefixes and investor mapping
- **Relative API Endpoints**: Uses `/api/search/multimodal` for deployment flexibility

## Clean V2 Enhancements
- ✅ **Removed problematic UI dependencies**: Eliminated shadcn/ui components causing build errors
- ✅ **Simplified build process**: Removed TypeScript compilation step from build
- ✅ **Native HTML inputs**: Replaced custom Input components with standard HTML inputs
- ✅ **Clean Vite config**: Removed unnecessary path aliases and Node.js imports  
- ✅ **Fixed unused variables**: Cleaned up TypeScript warnings and errors
- ✅ **Production-ready**: Builds successfully without dependency issues
- ✅ **Maintained functionality**: All search and UI features preserved
- ✅ **Optimized dependencies**: Minimal package.json with only required dependencies

## Installation

1. Install dependencies:
```bash
npm install
```

2. Start development server:
```bash
npm run dev
```

3. Build for production:
```bash
npm run build
```

## API Configuration
- **Endpoint**: `/api/search/multimodal` (relative)
- **Method**: POST
- **Content-Type**: application/json
- Works with any domain where the app is deployed

## Search Capabilities

### Text Search (Local)
- Exact keyword matching in German
- Fuzzy matching for typos and variations
- German singular/plural handling ("Socke" ↔ "Socken")
- Context-based search through product descriptions
- Tag-based discovery with German synonyms
- Searches in: name, description, category, investor, season, episode, tags, context

### Image Search (API)
- Visual similarity matching via `/api/search/multimodal`
- Optimized threshold (0.3) for balanced precision/recall
- Staffel 18 filtering applied to results
- Preserves original dataset for subsequent text searches

### German Search Examples
- `trinken` → bottles, drink containers
- `wellness` → health and fitness products  
- `tierbedarf` → pet products, dog harnesses
- `pflege` → skincare, beauty products
- `smart` → sensors, technology products
- `langlebig` → durable materials like steel
- `weich` → soft textiles, cotton products

## Enhanced Tag System
Products automatically get comprehensive German tags:

**Category Tags:**
- Gesundheit → wellness, fitness, körper, wohlbefinden, medizin
- Sport → training, bewegung, aktivität, übung, sportgerät
- Tech → technologie, innovation, digital, elektronik, gerät

**Product-Specific Tags:**
- Flasche → trinken, getränk, behälter, wasser, flüssigkeit
- Socke → füße, textil, kleidung, bekleidung, strümpfe
- Kapseln → nahrungsergänzung, gesundheit, supplement, vitamine

**Material Tags:**
- Edelstahl → metall, rostfrei, stahl, langlebig
- Baumwolle → textil, stoff, natürlich, weich

## Project Structure
```
src/
├── App.tsx                 # Main application with all UI logic
├── services/
│   ├── api.ts             # API service with relative endpoints
│   └── productMapper.ts   # Product mapping and German tag generation
├── components/            # Minimal UI components (figma components only)
└── main.tsx              # Application entry point
```

## Technical Details
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite
- **Styling**: Tailwind CSS
- **Animations**: Framer Motion
- **Icons**: Lucide React
- **API**: Relative endpoints for deployment flexibility
- **Search**: Hybrid local/remote search system
- **Language**: Optimized for German users

## Deployment
Since the API uses relative endpoints (`/api/search/multimodal`), this app can be deployed to any domain without configuration changes. Just ensure your backend API is available at the same domain.

---

*Clean V2 - January 2025*  
*Production-ready build with optimized dependencies and no build errors*