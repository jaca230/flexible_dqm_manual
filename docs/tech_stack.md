# Technology Stack

This page summarizes the core technologies, frameworks, and libraries used in this project, organized by the level of the system in which they operate.

---

## ZeroMQ Publisher (C++)

### Overview

A high-performance, highly configurable C++ application for real-time data processing, analysis, and publishing over ZeroMQ sockets. While most common use cases interface with MIDAS, the system is modular and does not require it—alternative input sources can be used via dedicated branches or "processors".

### Core Technologies

| Technology | Purpose | Learn More |
|------------|---------|------------|
| **ZeroMQ** | High-performance messaging library used for sending event data from the C++ publisher to the Python backend. | [ZeroMQ Documentation](https://zeromq.org/) |
| **analysis_pipeline** | Custom C++ framework for structuring real-time data pipelines. Uses Intel TBB for parallel execution and ROOT’s reflection system to dynamically load plugin stages and data products derived from TObject. Available plugins to interact with midas data. | [analysis_pipeline Documentation](https://github.com/jaca230/analysis_pipeline) |
| **ROOT** | ROOT is a C++ framework widely used in high-energy physics for data processing, analysis, and visualization. In this project, it is used for reflection, serialization, plugin support, and defining TObjects that stages and plugins operate on to enable dynamic, configurable data pipelines. | [ROOT Documentation](https://root.cern/) |
| **Intel TBB (Threading Building Blocks)** | Task-based parallelism and multithreading in C++. In this project it is used to create flow graphs that allow for parallelizable "pipelines" to pre-process published data at a low level. | [TBB Documentation](https://www.threadingbuildingblocks.org/) |
| **MIDAS**  | Data acquisition framework for reading and managing events from experiment hardware, providing structured event and bank access for downstream processing. In this project, we often assume our data comes from a MIDAS experiment. | [MIDAS Documentation](https://midas.triumf.ca/) |

---

## ZeroMQ Receiver and FastAPI Webserver (Python)

### Overview

Python-based backend responsible for receiving event data from the C++ publisher via ZeroMQ, buffering and processing it as needed, and serving it over HTTP endpoints for frontend visualization.

### Core Technologies

| Technology  | Purpose                                                                                                              | Learn More                                             |
| ----------- | -------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------ |
| **FastAPI** | Modern, high-performance Python framework used to build RESTful APIs and serve processed event data to the frontend. | [FastAPI Documentation](https://fastapi.tiangolo.com/) |
| **ZeroMQ**  | Messaging library used to receive high-throughput event streams from the C++ publisher.                              | [ZeroMQ Documentation](https://zeromq.org/)            |


---

## Data Quality Monitor Webapp (JavaScript / React)

### Overview

High-level frontend web application for interactive visualization of collected and processed data.

### Core Technologies

| Technology | Purpose | Learn More |
|------------|---------|------------|
| **React** | Component-based library for building dynamic user interfaces. | [React Documentation](https://reactjs.org/) |
| **react-plotly.js** | React wrapper for Plotly.js, enabling interactive charts and visualizations. | [react-plotly.js Documentation](https://github.com/plotly/react-plotly.js) |

---
