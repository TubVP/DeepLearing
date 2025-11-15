
# DeepLearning - Project

Đây là dự án bài tập lớn DL do NLQT phát triển, sử dụng mô hình LLM deepseek-coder-1.3b nhằm tối ưu code và tài nguyên sử dụng.

# Các file
*download file DL.zip rồi giải nén

*Tại đây sẽ chỉ tương tác với file 2025_UET_DL, chia ra làm các phần:

- model_weights: mô hình trọng số
- problems: lưu trữ các problem, test, solution
- file tesst1 là file chỉ để test, thực hiện các công việc ngoài do dev code, không cần quan tâm
- file uet_coder.py là file code chính, load mô hình, gene code 
- file uet_marker.py là file chấm điểm

# Chi tiết - cách khởi động 
- Do pytorch_model.bin là model rất nặng nên không thể push lên github repo, phải tải thủ công về bằng cách: vào link [deepseek-coder-1.3b](https://huggingface.co/deepseek-ai/deepseek-coder-1.3b-base/tree/main) rồi download về ném vào mô hình trọng số (folder model_weights).

*Cách khởi động
- mở cmd tại 2025_UET_DL
- với mỗi problem thì chạy số hiệu problem và solution tương ứng trên cmd, ví dụ với problem01: 
```bash
python uet_coder.py --problem problems/problem01/problem.md --output problems/problem01/solutions/solution01.py
```
- Nó sẽ chạy được như sau:
![D1](https://github.com/TubVP/test/blob/bee9ef466919609c308bdcbbf8c703e1444526cc/D1.png?raw=true)

- Nếu không chạy được hoặc cmd bị đứng hình, restart vscode và check file tesst1.ipynb, mọi thư viện mà dev sử dụng đều ở đó, còn lại thì hỏi gpt.

- có thể kiểm tra kết quả solution tương ứng bằng code trên cmd:
```bash
python .\uet_marker.py --source_code_file .\problems\problem01\solutions\solution01.py --test_cases .\problems\problem01\test01.json
```
- Hiện tại chỉ có 5 problem để test, có thể bổ sung thêm để kiểm tra chất lượng model

*Vấn đề còn tồn đọng:
- Hiện tại code chỉ kiểm tra được generation time, chưa thể kiểm tra 2 điều kiện sau:

-The solutions must use less than 100MB of memory.

-The solutions must run in less than 10 seconds.

