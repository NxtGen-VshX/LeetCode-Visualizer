# 🎯 LeetCode Algorithm Visualizer

A comprehensive, interactive web-based tool to visualize and understand complex LeetCode algorithms in real-time. Built with React and Go, this project demonstrates deep algorithmic knowledge through visual, step-by-step execution.

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Go Version](https://img.shields.io/badge/go-1.21+-blue.svg)
![React](https://img.shields.io/badge/react-18.2+-blue.svg)

## 🌟 Features

### Implemented Algorithms

1. **Median of Two Sorted Arrays** (Hard)
   - Binary search visualization
   - Partition animation
   - Step-by-step explanation
   - O(log(min(m,n))) complexity

2. **Regular Expression Matching** (Hard)
   - Dynamic programming table visualization
   - State transitions
   - Pattern matching animation
   - Interactive DP grid

3. **Count Square Submatrices** (Medium)
   - DP table construction
   - Square counting visualization
   - Real-time matrix updates
   - Formula explanation

4. **Count Submatrices With All Ones** (Medium)
   - Histogram approach visualization
   - Height array animation
   - Rectangle counting logic
   - Multiple algorithm comparisons

5. **Minimum Area Rectangle** (Medium)
   - Bounding box visualization
   - Interactive grid
   - Real-time area calculation
   - Geometric proof demonstration

## 🚀 Live Demo

### Quick Start (Frontend Only)
```bash
cd frontend
npm install
npm start
```
Visit `http://localhost:3000`

### Full Stack (Frontend + Backend)
```bash
# Terminal 1: Start backend
cd backend
go run main.go

# Terminal 2: Start frontend
cd frontend
npm start
```

## 📁 Project Structure

```
leetcode-visualizer/
├── frontend/                 # React application
│   ├── src/
│   │   ├── components/       # Algorithm visualizers
│   │   │   ├── MedianFinder.jsx
│   │   │   ├── RegexMatcher.jsx
│   │   │   ├── SquareCounter.jsx
│   │   │   ├── SubmatrixCounter.jsx
│   │   │   └── MinAreaFinder.jsx
│   │   ├── algorithms/       # Core algorithm implementations
│   │   │   ├── medianTwoArrays.js
│   │   │   ├── regexMatching.js
│   │   │   ├── countSquares.js
│   │   │   ├── countSubmatrices.js
│   │   │   └── minimumArea.js
│   │   ├── App.jsx
│   │   └── index.js
│   └── package.json
│
├── backend/                  # Go API server
│   ├── handlers/             # HTTP handlers
│   │   ├── median.go
│   │   ├── regex.go
│   │   ├── squares.go
│   │   ├── submatrices.go
│   │   └── minarea.go
│   ├── algorithms/           # Algorithm implementations
│   │   ├── median_arrays.go
│   │   ├── regex_match.go
│   │   ├── count_squares.go
│   │   ├── count_submatrices.go
│   │   └── minimum_area.go
│   ├── main.go
│   └── go.mod
│
├── docs/                     # Documentation
│   ├── ALGORITHMS.md         # Algorithm explanations
│   ├── API.md                # API documentation
│   └── CONTRIBUTING.md
│
└── README.md
```

## 🎨 Features Breakdown

### 1. Interactive Visualizations
- **Step-by-step execution**: See algorithms run in slow motion
- **Pause/Resume**: Control execution speed
- **Highlight active elements**: Visual feedback on current operation
- **Custom inputs**: Test with your own data

### 2. Educational Tools
- **Complexity analysis**: Visual representation of time/space complexity
- **Code snippets**: View implementation in multiple languages
- **Explanations**: Detailed breakdown of each step
- **Related problems**: Links to similar LeetCode questions

### 3. Performance Metrics
- **Execution time**: Real-time performance tracking
- **Operation count**: Number of comparisons/operations
- **Memory usage**: Space complexity visualization
- **Optimization comparison**: Compare different approaches

## 🛠️ Tech Stack

### Frontend
- **React 18**: Modern UI framework
- **Tailwind CSS**: Utility-first styling
- **Lucide React**: Beautiful icons
- **Recharts**: Data visualization
- **Framer Motion**: Smooth animations

### Backend
- **Go 1.21+**: High-performance server
- **Gorilla Mux**: HTTP routing
- **CORS support**: Cross-origin requests
- **JSON API**: RESTful endpoints

## 📖 Algorithm Details

### Median of Two Sorted Arrays
```
Time Complexity: O(log(min(m,n)))
Space Complexity: O(1)

Key Concept: Binary search on partition point
Why it works: Finding correct partition divides arrays optimally
```

### Regular Expression Matching
```
Time Complexity: O(m × n)
Space Complexity: O(m × n)

Key Concept: Dynamic programming with state transitions
Why it works: Optimal substructure - dp[i][j] depends on previous states
```

### Count Square Submatrices
```
Time Complexity: O(m × n)
Space Complexity: O(m × n)

Key Concept: dp[i][j] = size of largest square = count of squares
Why it works: Mathematical property - k×k square contains k smaller squares
```

### Count Submatrices With All Ones
```
Time Complexity: O(m × n²) basic, O(m × n) optimized
Space Complexity: O(n)

Key Concept: Convert to histogram problem
Why it works: Each row forms a histogram, count rectangles in O(n²)
```

### Minimum Area Rectangle
```
Time Complexity: O(m × n)
Space Complexity: O(1)

Key Concept: Bounding box is always minimum
Why it works: Geometric proof - cannot exclude extreme points
```

## 🎯 Usage Examples

### Example 1: Median of Two Arrays
```javascript
// Frontend
const nums1 = [1, 3, 5];
const nums2 = [2, 4, 6];

// Visual output shows:
// 1. Binary search iterations
// 2. Partition points
// 3. Median calculation
// Result: 3.5
```

### Example 2: Regex Matching
```javascript
// Frontend
const string = "aab";
const pattern = "c*a*b";

// Visual output shows:
// 1. DP table construction
// 2. State transitions
// 3. Final result
// Result: true
```

## 🔧 API Endpoints

### POST /api/median
```json
{
  "nums1": [1, 3],
  "nums2": [2, 4]
}

Response: {
  "median": 2.5,
  "steps": [...],
  "complexity": "O(log(min(m,n)))"
}
```

### POST /api/regex
```json
{
  "string": "aa",
  "pattern": "a*"
}

Response: {
  "match": true,
  "dpTable": [...],
  "steps": [...]
}
```

## 🚀 Deployment

### Docker Deployment
```bash
# Build and run with Docker
docker build -t leetcode-visualizer .
docker run -p 8080:8080 -p 3000:3000 leetcode-visualizer
```

### Manual Deployment
```bash
# Build frontend
cd frontend
npm run build

# Build backend
cd backend
go build -o server

# Run
./server
```

## 🤝 Contributing

Contributions are welcome! Please read [CONTRIBUTING.md](docs/CONTRIBUTING.md) for details.

### Adding New Algorithms
1. Implement algorithm in `backend/algorithms/`
2. Create handler in `backend/handlers/`
3. Build React component in `frontend/src/components/`
4. Add route and navigation
5. Write documentation

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Your Name**
- GitHub: [@cybervarsh](https://github.com/NxtGen-VshX/)
- LeetCode: [@cybervarsh](https://leetcode.com/NetGen-VshX/)

## 🙏 Acknowledgments

- LeetCode for problem inspiration
- React community for excellent tools
- Go community for performance libraries

## 📊 Project Stats

- **5 Complex Algorithms**: Hard & Medium difficulty
- **Interactive Visualizations**: Real-time animations
- **Full Stack**: React + Go
- **Production Ready**: Dockerized deployment
- **Well Documented**: Comprehensive guides

## 🔮 Future Enhancements

- [ ] Add more algorithms (graph, tree, string)
- [ ] User authentication and saved visualizations
- [ ] Algorithm comparison mode
- [ ] Export visualizations as videos
- [ ] Mobile responsive design
- [ ] Dark mode support
- [ ] Multi-language code snippets
- [ ] Performance benchmarking

---

⭐ Star this repository if you found it helpful!
