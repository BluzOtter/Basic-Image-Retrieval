## Step 1: Crawl urls chứa ảnh từ web về, lưu thành file txt.
Gửi request đến trang freeimages.com, lưu các đường dẫn của ảnh vào file txt theo từng topic.

`python utils/crawl_urls_to_txts.py` 

## Step 2: Lấy ảnh từ file txt đã crawl từ step 1.
Tải các hình ảnh theo từng topic vào các thư mục với tên tương ứng với từng topic

`python utils/get_images_from_txts.py`

## Step 3: Tiền xử lý các file ảnh ở step 2.
- Loại bỏ những hình ảnh lỗi (Không đọc được ảnh,...)

- Loại bỏ những hình ảnh có kích thước nhỏ hơn 10

- Loại bỏ hình ảnh có channel khác 3 (chỉ nhận ảnh màu RGB)

`python utils/preprocessingData.py`

## Step 4: 
- Lưu data đã được xử lý vào folder static/images
- Tải [weight_resnet50](https://drive.google.com/file/d/1MGnNmnh7evfATsSSJTWcB-IPE36IVZ40/view?usp=share_link)
- Sau đó chạy file feature_extractor.py để trích xuất feature tập dataset. Sau khi chạy xong thu được 1 file tại feature/all_features.npz 

`python feature_extractor.py`
