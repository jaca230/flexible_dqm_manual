# Technology Stack

This page summarizes the core technologies, frameworks, and libraries used in this project, organized by the level of the system they operate in.

---

## Low-Level C++ (Real-Time Data Collectors / Analyzers)

| Technology | Description | Learn More |
|------------|-------------|------------|
| **ROOT** | Framework for data processing, analysis, and visualization commonly used in high-energy physics. | [ROOT Documentation](https://root.cern/) |
| **TBB (Threading Building Blocks)** | Intel's library for task-based parallelism and multithreading in C++. | [TBB Documentation](https://www.threadingbuildingblocks.org/) |
| **analysis_pipeline** | Custom C++ framework for organizing real-time data processing pipelines. | *(internal framework; no external link)* |

**Application / Use in Project:**  
*TODO: Describe how ROOT, TBB, and analysis_pipeline are used specifically in your project.*

---

## Mid-Level Python (Backend / Web Server)

| Technology | Description | Learn More |
|------------|-------------|------------|
| **FastAPI** | Modern, high-performance Python web framework for building APIs. | [FastAPI Documentation](https://fastapi.tiangolo.com/) |

**Application / Use in Project:**  
*TODO: Describe how FastAPI is used to serve data to the frontend and interface with data buffers.*

---

## High-Level JavaScript (Frontend / Web Application)

| Technology | Description | Learn More |
|------------|-------------|------------|
| **React** | JavaScript library for building interactive user interfaces. | [React Documentation](https://reactjs.org/) |
| **React Plotly** | React wrapper for Plotly.js, used to create interactive charts and plots within React components. | [react-plotly.js Documentation](https://github.com/plotly/react-plotly.js) |

**Application / Use in Project:**  
*TODO: Describe how React and React Plotly are used to visualize the data collected and processed by the backend.*

---

This structure helps provide a clear overview of your tech stack while leaving space to describe its specific application within the project.
