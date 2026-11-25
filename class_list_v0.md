# Danh sách lớp v0 — Đỗ Anh Hoàng · G09

## DMS

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng DMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | person / seat | driver | Xác định người lái và vùng người cần theo dõi | Có, chủ yếu theo hình dáng |
| 2 | face / eye_left, eye_right | open / closed / unknown | Theo dõi trạng thái mắt để hỗ trợ phát hiện buồn ngủ | Có thể; phản xạ kính hoặc che khuất làm giảm độ tin cậy |
| 3 | face / gaze_zone | road, mirror_l, mirror_r, mirror_c, cluster, center, lap, other | Phát hiện tài xế nhìn khỏi đường hoặc nhìn vùng cần chú ý | Một phần; hướng đầu/mắt có thể quan sát được nhưng không phải lúc nào cũng rõ |
| 4 | face / glasses | unknown, none, clear, sun | Nhận biết kính có thể che mắt và ảnh hưởng độ tin cậy của theo dõi mắt | Một phần; NIR không luôn phân biệt được kính trong và kính râm |
| 5 | face13 | 13 điểm mặt; từng điểm visible, occluded hoặc outside | Ước lượng tư thế mặt và vị trí các đặc trưng khuôn mặt | Một phần; phản xạ, che khuất và góc mặt có thể làm mất điểm |
| 6 | hand / side, on_wheel | left, right; yes, no, unknown | Nhận biết tay tài xế và việc tay có tiếp xúc vô lăng hay không | Thường có theo hình dáng/vị trí; vật tối hoặc che khuất gây khó |
| 7 | phone / state | held, mounted, lap | Phát hiện việc sử dụng điện thoại trong cabin | Thường có theo hình dáng; ảnh tối/che khuất có thể gây nhầm |

## OMS

| # | Lớp / thuộc tính | Giá trị | Để làm gì (chức năng OMS) | Nhìn thấy được trên IR? |
|---|---|---|---|---|
| 1 | person / seat | driver, front_passenger, rear_left, rear_middle, rear_right | Đếm người và xác định vị trí ngồi | Có thể theo hình dáng và vị trí; ghế phải gọi theo xe |
| 2 | seatbelt | worn_correct, worn_incorrect, not_worn, unknown | Theo dõi việc sử dụng dây an toàn | Một phần; dây có thể chìm vào nền hoặc bị che |
| 3 | child_seat / occupied | occupied: no hoặc unknown; seat | Nhận biết ghế trẻ em và tình trạng nhìn thấy bên trong | Thường nhận ra hình dáng ghế; tình trạng bên trong có thể không rõ |
| 4 | infant_seat / facing | rear hoặc front; seat | Nhận biết nôi/ghế em bé và hướng quay | Thường có theo hình dáng |
| 5 | object / type | bag, box, cup, other; seat | Nhận biết đồ vật trong cabin để hỗ trợ quản lý bố trí/chiếm chỗ | Hình dáng thường còn thấy; màu sắc không đáng tin trên IR |
| 6 | frame_meta / modality, light, camera_blocked | rgb/ir; day/night/unknown; yes/no | Ghi ngữ cảnh ảnh để diễn giải nhãn và chất lượng quan sát | Có từ loại ảnh/quan sát; không suy màu từ ảnh IR |

## 2 câu hỏi leo thang

1. Câu hỏi: Khi một phần bên trong ghế trẻ em bị che, tiêu chí nào đủ để chọn `occupied=no` thay vì `unknown`?
   Khung ví dụ: S02_ir.png.
   Dùng `unknown` nếu không nhìn rõ bên trong; chỉ dùng `no` khi xác nhận ghế trống.
2. Câu hỏi: Khi mắt không quan sát rõ nhưng vị trí điểm mặt có thể ước lượng, nên đánh `occluded` hay `outside`?
   Khung ví dụ: D06.png.
   Dùng `occluded` nếu có thể ước lượng vị trí bị che; dùng `outside` nếu không thể đoán vị trí.
