# 🗒️ Workflow Tracker - Kanban Board

<div align="center">

**A modern, interactive Kanban board for managing your workflow efficiently**

[![Next.js](https://img.shields.io/badge/Next.js-14.2-black?style=flat-square&logo=next.js)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-18-blue?style=flat-square&logo=react)](https://reactjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-blue?style=flat-square&logo=typescript)](https://www.typescriptlang.org/)
[![Framer Motion](https://img.shields.io/badge/Framer_Motion-11.11-pink?style=flat-square&logo=framer)](https://www.framer.com/motion/)
[![License](https://img.shields.io/badge/License-MIT-green?style=flat-square)](LICENSE)

[Demo](https://noelregis718.github.io/Workflow-Tracker) · [Report Bug](https://github.com/noelregis718/Workflow-Tracker/issues) · [Request Feature](https://github.com/noelregis718/Workflow-Tracker/issues)

</div>

---

## 📋 Table of Contents

- [About](#-about)
- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Getting Started](#-getting-started)
- [Usage](#-usage)
- [Technical Highlights](#-technical-highlights)
- [Project Structure](#-project-structure)
- [Roadmap](#-roadmap)
- [Contributing](#-contributing)
- [Author](#-author)
- [License](#-license)

---

## 🎯 About

**Workflow Tracker** is a sleek, modern Kanban board application built with Next.js and Framer Motion. It provides an intuitive drag-and-drop interface for managing tasks across different stages of your workflow. Whether you're managing personal projects, team tasks, or daily to-dos, this application offers a seamless experience with smooth animations and responsive design.

### Why Workflow Tracker?

- **🎨 Beautiful UI**: Clean, modern interface with smooth animations
- **🚀 Fast & Responsive**: Built with Next.js for optimal performance
- **📱 Desktop-First**: Optimized for desktop drag-and-drop interactions
- **🎭 Smooth Animations**: Powered by Framer Motion for fluid transitions
- **💾 Local Storage**: Your tasks persist across sessions
- **🔧 Customizable**: Easy to extend and customize to your needs

---

## ✨ Features

### Core Functionality

- ✅ **Drag & Drop Interface** - Intuitive card movement between columns
- ✅ **Multiple Columns** - Organize tasks by status (Backlog, TODO, In Progress, Complete)
- ✅ **Add/Edit/Delete Tasks** - Full CRUD operations for task management
- ✅ **Persistent Storage** - Tasks saved to local storage automatically
- ✅ **Smooth Animations** - Framer Motion powered transitions and layouts
- ✅ **Responsive Design** - Optimized for various screen sizes

### User Experience

- 🎯 **Quick Task Creation** - Add tasks with a single click
- 🎨 **Visual Feedback** - Hover effects and drag indicators
- ⚡ **Real-time Updates** - Instant UI updates without page refresh
- 🔄 **Auto-save** - Changes saved automatically

---

## 🛠️ Tech Stack

| Technology | Purpose | Version |
|------------|---------|---------|
| **[Next.js](https://nextjs.org/)** | React Framework | 14.2.15 |
| **[React](https://reactjs.org/)** | UI Library | 18.x |
| **[TypeScript](https://www.typescriptlang.org/)** | Type Safety | 5.x |
| **[Framer Motion](https://www.framer.com/motion/)** | Animation Library | 11.11.9 |
| **[Tailwind CSS](https://tailwindcss.com/)** | Styling | 3.4.1 |
| **[React Icons](https://react-icons.github.io/react-icons/)** | Icon Library | 5.3.0 |

---

## 🚀 Getting Started

### Prerequisites

Before you begin, ensure you have the following installed:

- **Node.js** (v18 or higher)
- **npm**, **yarn**, **pnpm**, or **bun** package manager

### Installation

1. **Clone the repository**

```bash
git clone https://github.com/noelregis718/Workflow-Tracker.git
cd Workflow-Tracker/kanban-board
```

2. **Install dependencies**

```bash
npm install
# or
yarn install
# or
pnpm install
# or
bun install
```

3. **Run the development server**

```bash
npm run dev
# or
yarn dev
# or
pnpm dev
# or
bun dev
```

4. **Open your browser**

Navigate to [http://localhost:3000](http://localhost:3000) to see the application in action.

### Build for Production

```bash
npm run build
npm start
```

---

## 💡 Usage

### Creating a Task

1. Click the **"+ Add card"** button in any column
2. Enter your task description
3. Press **Enter** or click outside to save

### Moving Tasks

1. **Click and hold** on a task card
2. **Drag** the card to the desired column
3. **Release** to drop the card in the new position

### Editing Tasks

1. Click on the task text
2. Edit the content
3. Press **Enter** or click outside to save

### Deleting Tasks

1. Hover over a task card
2. Click the **delete icon** (🗑️)
3. Confirm deletion

---

## 🔬 Technical Highlights

### Custom Data Attributes

The application leverages HTML5 custom data attributes for efficient data management:

```html
<div
  data-id="123"
  data-column="todo"
  data-name="Task Name"
>
  Task Content
</div>
```

This approach allows for:
- Easy retrieval of task metadata during drag operations
- Clean separation of data and presentation
- Improved performance by avoiding excessive state lookups

### Event Metadata Handling

Every drag event carries contextual metadata, enabling precise control over:
- **Source column** - Where the drag started
- **Target column** - Where the card is being dropped
- **Card position** - Index within the column
- **Card data** - Task content and properties

### Framer Motion Integration

#### Layout Animations

Framer Motion's `layout` attribute handles automatic animations without explicit configuration:

```jsx
<motion.div layout>
  {/* Content automatically animates on layout changes */}
</motion.div>
```

#### Layout IDs

Each card uses a unique `layoutId` for smooth transitions between positions:

```jsx
<motion.div layoutId={card.id}>
  {/* Framer Motion tracks this element across re-renders */}
</motion.div>
```

### Performance Optimizations

- **useCallback** - Memoized function references prevent unnecessary re-renders
- **Prop Drilling** - Limited to 2 layers for maintainability
- **Efficient Re-renders** - Only affected components update on state changes

---

## 📁 Project Structure

```
kanban-board/
├── src/
│   ├── app/
│   │   ├── page.tsx          # Main Kanban board component
│   │   ├── layout.tsx        # Root layout
│   │   └── globals.css       # Global styles
│   └── components/           # Reusable components
├── public/                   # Static assets
├── .eslintrc.json           # ESLint configuration
├── next.config.mjs          # Next.js configuration
├── tailwind.config.ts       # Tailwind CSS configuration
├── tsconfig.json            # TypeScript configuration
├── package.json             # Dependencies and scripts
└── README.md                # Project documentation
```

---

## 🗺️ Roadmap

### Planned Features

- [ ] **Authentication** - SSO layer for user login
- [ ] **Cloud Storage** - Remote database integration for cross-device sync
- [ ] **Mobile Support** - Touch-based drag and drop for mobile devices
- [ ] **Collaboration** - Real-time multi-user editing
- [ ] **Task Priority** - Color-coded priority levels
- [ ] **Due Dates** - Deadline tracking and notifications
- [ ] **Tags & Labels** - Categorize tasks with custom tags
- [ ] **Search & Filter** - Find tasks quickly
- [ ] **Dark Mode** - Theme customization
- [ ] **Export/Import** - Backup and restore functionality

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork** the repository
2. **Create** a feature branch (`git checkout -b feature/AmazingFeature`)
3. **Commit** your changes (`git commit -m 'Add some AmazingFeature'`)
4. **Push** to the branch (`git push origin feature/AmazingFeature`)
5. **Open** a Pull Request

Please ensure your code follows the existing style and includes appropriate tests.

---

## 👨‍💻 Author

**Noel Regis**

- 📧 Email: [noelregis718@gmail.com](mailto:noelregis718@gmail.com)
- 🐙 GitHub: [@noelregis718](https://github.com/noelregis718)
- 🌐 Portfolio: [Coming Soon]

---

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- Built with [Next.js](https://nextjs.org/)
- Animations powered by [Framer Motion](https://www.framer.com/motion/)
- Icons from [React Icons](https://react-icons.github.io/react-icons/)
- Styled with [Tailwind CSS](https://tailwindcss.com/)

---

<div align="center">

**⭐ Star this repository if you find it helpful!**

Made with ❤️ by [Noel Regis](https://github.com/noelregis718)

</div>
