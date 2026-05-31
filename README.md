# Chatbot Hỗ Trợ Hành Chính Công (RAG)

## Giới thiệu

Dự án xây dựng chatbot hỗ trợ tra cứu thông tin hành chính công bằng kỹ thuật Retrieval-Augmented Generation (RAG). Hệ thống có khả năng tìm kiếm thông tin từ tập tài liệu nghiệp vụ, sau đó sử dụng mô hình ngôn ngữ lớn để tạo câu trả lời chính xác và phù hợp với ngữ cảnh.

## Tính năng chính

* Chuyển đổi tài liệu DOCX sang Markdown tự động.
* Tiền xử lý và chia nhỏ tài liệu thành các chunk.
* Sinh vector embedding bằng OpenAI Embedding Model.
* Lưu trữ dữ liệu vector trong ChromaDB.
* Tìm kiếm ngữ nghĩa (Semantic Search).
* Viết lại câu hỏi (Query Rewriting) để cải thiện khả năng truy xuất.
* Re-ranking tài liệu nhằm tăng độ chính xác của kết quả tìm kiếm.
* Sinh câu trả lời dựa trên ngữ cảnh được truy xuất.
* Trực quan hóa embedding bằng t-SNE 2D và 3D.

## Kiến trúc hệ thống

DOCX Files
↓
Markdown Conversion
↓
Chunking
↓
OpenAI Embeddings
↓
ChromaDB Vector Store
↓
Semantic Retrieval
↓
Query Rewriting
↓
Re-ranking
↓
LLM Generation
↓
Final Answer

## Công nghệ sử dụng

* Python
* OpenAI API
* ChromaDB
* MarkItDown
* LiteLLM
* Pydantic
* Scikit-learn
* Plotly
* Gradio
* TQDM

## Quy trình hoạt động

### 1. Xử lý dữ liệu

* Đọc tài liệu hành chính công dạng DOCX.
* Chuyển đổi sang Markdown.
* Thu thập metadata từ tài liệu.

### 2. Chunking

Tài liệu được chia thành các đoạn nhỏ với:

* Chunk Size: 1500 ký tự
* Overlap: 200 ký tự

### 3. Tạo Embedding

Sử dụng:

text-embedding-3-large

để chuyển đổi văn bản thành vector biểu diễn ngữ nghĩa.

### 4. Lưu trữ Vector

Các embedding được lưu vào ChromaDB để phục vụ truy xuất nhanh.

### 5. Truy xuất tài liệu

Khi người dùng đặt câu hỏi:

* Sinh embedding cho câu hỏi.
* Tìm kiếm các chunk tương đồng trong ChromaDB.

### 6. Query Rewriting

Câu hỏi được viết lại nhằm:

* Làm rõ ý định người dùng.
* Tăng khả năng truy xuất đúng tài liệu.

### 7. Re-ranking

Các chunk tìm được sẽ được sắp xếp lại theo mức độ liên quan bằng LLM trước khi đưa vào ngữ cảnh.

### 8. Sinh câu trả lời

Mô hình GPT sử dụng:

* Câu hỏi của người dùng.
* Các chunk liên quan nhất.

để tạo câu trả lời cuối cùng.

## Trực quan hóa dữ liệu

Dự án hỗ trợ:

* t-SNE 2D
* t-SNE 3D

để quan sát sự phân bố của các vector embedding trong không gian ngữ nghĩa.

## Cấu trúc thư mục

```text
project/
│
├── database/
│   └── *.docx
│
├── markdown_files/
│   └── *.md
│
├── vector_db/
│
├── chatbot.ipynb
│
└── README.md
```

## Cài đặt

```bash
pip install openai
pip install chromadb
pip install markitdown
pip install litellm
pip install plotly
pip install scikit-learn
pip install gradio
pip install tqdm
pip install python-dotenv
```

## Thiết lập môi trường

Tạo file `.env`
# Chatbot Hỗ Trợ Hành Chính Công (RAG)

## Giới thiệu

Dự án xây dựng chatbot hỗ trợ tra cứu thông tin hành chính công bằng kỹ thuật Retrieval-Augmented Generation (RAG). Hệ thống có khả năng tìm kiếm thông tin từ tập tài liệu nghiệp vụ, sau đó sử dụng mô hình ngôn ngữ lớn để tạo câu trả lời chính xác và phù hợp với ngữ cảnh.

## Tính năng chính

* Chuyển đổi tài liệu DOCX sang Markdown tự động.
* Tiền xử lý và chia nhỏ tài liệu thành các chunk.
* Sinh vector embedding bằng OpenAI Embedding Model.
* Lưu trữ dữ liệu vector trong ChromaDB.
* Tìm kiếm ngữ nghĩa (Semantic Search).
* Viết lại câu hỏi (Query Rewriting) để cải thiện khả năng truy xuất.
* Re-ranking tài liệu nhằm tăng độ chính xác của kết quả tìm kiếm.
* Sinh câu trả lời dựa trên ngữ cảnh được truy xuất.
* Trực quan hóa embedding bằng t-SNE 2D và 3D.

## Kiến trúc hệ thống

DOCX Files
↓
Markdown Conversion
↓
Chunking
↓
OpenAI Embeddings
↓
ChromaDB Vector Store
↓
Semantic Retrieval
↓
Query Rewriting
↓
Re-ranking
↓
LLM Generation
↓
Final Answer

## Công nghệ sử dụng

* Python
* OpenAI API
* ChromaDB
* MarkItDown
* LiteLLM
* Pydantic
* Scikit-learn
* Plotly
* Gradio
* TQDM

## Quy trình hoạt động

### 1. Xử lý dữ liệu

* Đọc tài liệu hành chính công dạng DOCX.
* Chuyển đổi sang Markdown.
* Thu thập metadata từ tài liệu.

### 2. Chunking

Tài liệu được chia thành các đoạn nhỏ với:

* Chunk Size: 1500 ký tự
* Overlap: 200 ký tự

### 3. Tạo Embedding

Sử dụng:

text-embedding-3-large

để chuyển đổi văn bản thành vector biểu diễn ngữ nghĩa.

### 4. Lưu trữ Vector

Các embedding được lưu vào ChromaDB để phục vụ truy xuất nhanh.

### 5. Truy xuất tài liệu

Khi người dùng đặt câu hỏi:

* Sinh embedding cho câu hỏi.
* Tìm kiếm các chunk tương đồng trong ChromaDB.

### 6. Query Rewriting

Câu hỏi được viết lại nhằm:

* Làm rõ ý định người dùng.
* Tăng khả năng truy xuất đúng tài liệu.

### 7. Re-ranking

Các chunk tìm được sẽ được sắp xếp lại theo mức độ liên quan bằng LLM trước khi đưa vào ngữ cảnh.

### 8. Sinh câu trả lời

Mô hình GPT sử dụng:

* Câu hỏi của người dùng.
* Các chunk liên quan nhất.

để tạo câu trả lời cuối cùng.

## Trực quan hóa dữ liệu

Dự án hỗ trợ:

* t-SNE 2D
* t-SNE 3D

để quan sát sự phân bố của các vector embedding trong không gian ngữ nghĩa.

## Cấu trúc thư mục

```text
project/
│
├── database/
│   └── *.docx
│
├── markdown_files/
│   └── *.md
│
├── vector_db/
│
├── chatbot.ipynb
│
└── README.md
```

## Cài đặt

```bash
pip install openai
pip install chromadb
pip install markitdown
pip install litellm
pip install plotly
pip install scikit-learn
pip install gradio
pip install tqdm
pip install python-dotenv
```

## Thiết lập môi trường

Tạo file `.env`

```env
OPENAI_API_KEY=your_api_key
```

## Chạy dự án

Mở notebook:

```bash
jupyter notebook
```

hoặc

```bash
jupyter lab
```

Sau đó chạy tuần tự các cell trong notebook.

## Mục tiêu

Hỗ trợ người dân tra cứu thông tin hành chính công nhanh chóng, chính xác và dễ dàng thông qua công nghệ RAG kết hợp mô hình ngôn ngữ lớn.
# Chatbot Hỗ Trợ Hành Chính Công (RAG)

## Giới thiệu

Dự án xây dựng chatbot hỗ trợ tra cứu thông tin hành chính công bằng kỹ thuật Retrieval-Augmented Generation (RAG). Hệ thống có khả năng tìm kiếm thông tin từ tập tài liệu nghiệp vụ, sau đó sử dụng mô hình ngôn ngữ lớn để tạo câu trả lời chính xác và phù hợp với ngữ cảnh.

## Tính năng chính

* Chuyển đổi tài liệu DOCX sang Markdown tự động.
* Tiền xử lý và chia nhỏ tài liệu thành các chunk.
* Sinh vector embedding bằng OpenAI Embedding Model.
* Lưu trữ dữ liệu vector trong ChromaDB.
* Tìm kiếm ngữ nghĩa (Semantic Search).
* Viết lại câu hỏi (Query Rewriting) để cải thiện khả năng truy xuất.
* Re-ranking tài liệu nhằm tăng độ chính xác của kết quả tìm kiếm.
* Sinh câu trả lời dựa trên ngữ cảnh được truy xuất.
* Trực quan hóa embedding bằng t-SNE 2D và 3D.

## Kiến trúc hệ thống

DOCX Files
↓
Markdown Conversion
↓
Chunking
↓
OpenAI Embeddings
↓
ChromaDB Vector Store
↓
Semantic Retrieval
↓
Query Rewriting
↓
Re-ranking
↓
LLM Generation
↓
Final Answer

## Công nghệ sử dụng

* Python
* OpenAI API
* ChromaDB
* MarkItDown
* LiteLLM
* Pydantic
* Scikit-learn
* Plotly
* Gradio
* TQDM

## Quy trình hoạt động

### 1. Xử lý dữ liệu

* Đọc tài liệu hành chính công dạng DOCX.
* Chuyển đổi sang Markdown.
* Thu thập metadata từ tài liệu.

### 2. Chunking

Tài liệu được chia thành các đoạn nhỏ với:

* Chunk Size: 1500 ký tự
* Overlap: 200 ký tự

### 3. Tạo Embedding

Sử dụng:

text-embedding-3-large

để chuyển đổi văn bản thành vector biểu diễn ngữ nghĩa.

### 4. Lưu trữ Vector

Các embedding được lưu vào ChromaDB để phục vụ truy xuất nhanh.

### 5. Truy xuất tài liệu

Khi người dùng đặt câu hỏi:

* Sinh embedding cho câu hỏi.
* Tìm kiếm các chunk tương đồng trong ChromaDB.

### 6. Query Rewriting

Câu hỏi được viết lại nhằm:

* Làm rõ ý định người dùng.
* Tăng khả năng truy xuất đúng tài liệu.

### 7. Re-ranking

Các chunk tìm được sẽ được sắp xếp lại theo mức độ liên quan bằng LLM trước khi đưa vào ngữ cảnh.

### 8. Sinh câu trả lời

Mô hình GPT sử dụng:

* Câu hỏi của người dùng.
* Các chunk liên quan nhất.

để tạo câu trả lời cuối cùng.

## Trực quan hóa dữ liệu

Dự án hỗ trợ:

* t-SNE 2D
* t-SNE 3D

để quan sát sự phân bố của các vector embedding trong không gian ngữ nghĩa.

## Cấu trúc thư mục

```text
project/
│
├── database/
│   └── *.docx
│
├── markdown_files/
│   └── *.md
│
├── vector_db/
│
├── chatbot.ipynb
│
└── README.md
```

## Cài đặt

```bash
pip install openai
pip install chromadb
pip install markitdown
pip install litellm
pip install plotly
pip install scikit-learn
pip install gradio
pip install tqdm
pip install python-dotenv
```

## Thiết lập môi trường

Tạo file `.env`

```env
OPENAI_API_KEY=your_api_key
```

## Chạy dự án

Mở notebook:

```bash
jupyter notebook
```

hoặc

```bash
jupyter lab
```

Sau đó chạy tuần tự các cell trong notebook.

## Mục tiêu

Hỗ trợ người dân tra cứu thông tin hành chính công nhanh chóng, chính xác và dễ dàng thông qua công nghệ RAG kết hợp mô hình ngôn ngữ lớn.

```env
OPENAI_API_KEY=your_api_key
```

## Chạy dự án

Mở notebook:

```bash
jupyter notebook
```

hoặc

```bash
jupyter lab
```

Sau đó chạy tuần tự các cell trong notebook.

## Mục tiêu

Hỗ trợ người dân tra cứu thông tin hành chính công nhanh chóng, chính xác và dễ dàng thông qua công nghệ RAG kết hợp mô hình ngôn ngữ lớn.
