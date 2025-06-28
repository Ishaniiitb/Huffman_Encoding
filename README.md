# High-Throughput Canonical Huffman Encoder (VLSI Architecture)

## 📄 Summary

This repository summarizes the research work on a **high-throughput VLSI architecture** for **Canonical Huffman encoding**, as published in *IEEE Transactions on Circuits and Systems II: Express Briefs, Vol. 69, No. 1, Jan. 2022*.

## 🧠 Motivation

Traditional Huffman encoding requires two full passes over the data to:
- Gather symbol frequencies
- Generate the codeword table

This results in:
- Low encoding speed
- High hardware cost

The proposed design optimizes this by enabling **single-pass encoding** with **parallel hardware stages** for higher throughput and lower latency.

## 🚀 Key Contributions

- **Single-pass frequency statistics and sorting** using pipelined architecture
- **Parallel code-size computing and sorting**
- **Optimized code-size limiting** to reduce hardware area and delay
- **High-throughput VLSI architecture** capable of encoding in real-time

## 🛠 Architecture Overview

The design consists of three major pipeline stages:

1. **Frequency-Generation Stage**  
   - Performs real-time frequency statistics and sorting using 257 parallel update cells
   - Minimizes latency with pipelined updates

2. **Code-Size Computing & Sorting Stage**  
   - Constructs Huffman tree and calculates code sizes using FSM
   - Integrates sorting in parallel to avoid processing delays

3. **Code-Size-Limiting Stage**  
   - Optimizes canonical code assignment
   - Reduces look-up table size and logic delay

## 📊 Performance Highlights

| Metric                          | Proposed Architecture | Reference [11]    |
|---------------------------------|------------------------|-------------------|
| Encoding Time (256 symbols)     | 12,380 ns              | 16,800 ns         |
| Encoding Time (10,240 symbols)  | 44,315 ns              | 216,480 ns        |
| Avg. Time (Kodak24 dataset)     | 537,338.4 ns           | 4,264,517.5 ns    |
| Image Compression Improvement   | +12.24% (JPEG system)  | –                 |
| Area                            | 2,008,766 µm²          | 340,114 µm²       |
| Frequency                       | 400 MHz                | 50 MHz            |
| Power Consumption               | 850.84 mW              | –                 |

## 📘 Citation

```bibtex
@article{shao2022huffman,
  title={A High-Throughput VLSI Architecture Design of Canonical Huffman Encoder},
  author={Zhenyu Shao and Zhixiong Di and Quanyuan Feng and Qiang Wu and Yibo Fan and Xulin Yu and Wenqiang Wang},
  journal={IEEE Transactions on Circuits and Systems II: Express Briefs},
  volume={69},
  number={1},
  pages={209--213},
  year={2022},
  doi={10.1109/TCSII.2021.3091611}
}
