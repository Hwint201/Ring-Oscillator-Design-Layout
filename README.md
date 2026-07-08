# Ring-Oscillator-Design-Layout
Ring oscillator là mạch dao động đơn giản gồm một số lẻ N cổng đảo (inverter) mắc nối tiếp thành vòng kín (output của cổng cuối nối vào input của cổng đầu).
Mỗi inverter tạo ra một độ trễ tín hiệu; tổng độ trễ vòng gây ra điều kiện dao động tự duy trì. 

<img width="480" height="300" alt="image" src="https://github.com/user-attachments/assets/bbace77a-8fdf-494b-81a1-c96fd525aa06" />

Công thức tính toán:  $$f = \frac{1}{T} = \frac{1}{2Nt_{pd}}$$ 

# Schematic Ring-Oscillator

<img width="1299" height="521" alt="schematic_RING OSCILLATOR" src="https://github.com/user-attachments/assets/8a4ff2b8-97c4-49cc-a0e6-f97e2fc551f6" />

## Công nghệ & Thông số

Công nghệ: Generic 250nm

Công cụ thiết kế: Siemens Tanner EDA

Kiến trúc:Mạch dao động vòng 9 tầng (9-Stage CMOS Ring Oscillator)

Chiều rộng PMOS ($W_p$): 6µm

Chiều rộng NMOS ($W_n$): 3µmC

hiều dài kênh (L): 0.5µm

## Sóng pre_layout

<img width="2874" height="1331" alt="pre_layout" src="https://github.com/user-attachments/assets/09aa7529-cb0f-440c-aad3-35b3565c1dc9" />

# Layout hoàn chỉnh

<img width="2905" height="1350" alt="layout" src="https://github.com/user-attachments/assets/ac1799d6-91d7-4959-ae5a-767733bab2bd" />

## DRC 

<img width="2742" height="1348" alt="DRC" src="https://github.com/user-attachments/assets/09668151-1529-4337-ac81-e8844ae8024f" />

## LVS

<img width="2687" height="1267" alt="LVS" src="https://github.com/user-attachments/assets/bee69b42-68e3-4702-b8e3-a4fb60befec9" />

## Thành phần RC ký sinh 

<img width="2838" height="1320" alt="Thành phần RC" src="https://github.com/user-attachments/assets/e7bf98f6-f7b3-45d1-b322-6f02073d1324" />

## Post_layout

<img width="1322" height="772" alt="Post_layout" src="https://github.com/user-attachments/assets/1a978707-79a2-46ce-aedb-cc4c6c6c46bd" />

# Nhận xét chung 

| Yếu tố thay đổi | Xu hướng khi tăng | Nhận xét |
| :---| :--- | :--- |
| **Vdd** | - Biên độ sóng lớn hơn (gần 0 – Vdd)<br>- Cạnh lên/xuống dốc hơn (risetime, falltime giảm)<br>- Tần số dao động tăng | Dạng sóng vuông hơn, biên độ đầy đủ hơn. Nhưng công suất tiêu thụ tăng. |
| **Số tầng (N)** | - Chu kỳ tăng ($T \approx 2 \cdot N \cdot t_d$)<br>- Tần số giảm | Số tầng nhiều $\rightarrow$ transistor có thêm thời gian nạp/xả $\rightarrow$ sóng ít méo, vuông vức hơn, nhưng tốc độ chậm đi. |
| **Wp (W/L PMOS)** | PMOS mạnh hơn $\rightarrow$ cạnh lên nhanh hơn.<br>Nếu Wp quá lớn so với Wn $\rightarrow$ mất cân bằng (rise $\neq$ fall) | Chọn Wp/Wn hợp lý để cân bằng cạnh lên và xuống, sóng gần vuông. |
| **Không tụ tải** | - Dao động ở tần số cao<br>- Sóng có xu hướng méo, bo tròn nếu transistor không kịp nạp/xả | Sóng nhanh nhưng không thật vuông. |
| **Có tụ tải (CL)** | - Tần số giảm (do RC lớn hơn)<br>- Cạnh lên/xuống chậm hơn | Giúp sóng mượt và vuông vức hơn, nhưng tốc độ giảm. |




