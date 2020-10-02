# search
Mô tả cách làm:
- Question 1:
    Sử dụng Stack để lưu vị trí trạng thái và list các hành động đến trạng thái đó. Chúng ta sẽ duyệt từ trạng thái bắt đầu cho đến khi tìm được trạng thái đích. Trong quá trình duyệt sẽ lưu từng hành động qua từng trạng thái cho đến đích vào list của từng phần tử trong Stack. Một list khác không nằm trong Stack dùng để lưu những vị trí đã được duyệt nhằm không duyệt trùng lặp. Vì stack sẽ lấy ra phần tử mới được thêm vào trước nên có thể duyệt theo kiểu dfs.
- Question 2:
    Tương tự như Q1 nhưng thay vì dùng Stack, ta sử dụng Queue vì trong Queue nhũng phần tử được thêm vào trước sẽ được lấy ra trước nên sẽ duyệt theo kiểu bfs.
- Question 3:
    Tương tự 2 câu trên, nhưng với câu 3 ta sử dụng PriorityQueue với độ ưu tiên là tổng giá trị các bước để đi đến vị trí đang duyệt. Vị trí nào có tổng giá trị nhỏ hơn sẽ được ưu tiên hơn và xếp lên trước trong hàng đợi.
- Question 4:
    Tương tự Q3, nhưng độ ưu tiên ở Q4 là tổng giá trị các bước đến vị trí cộng với khoảng cách đến đích tại vị trí đó.
- Question 5:
    + Các trạng thái ở Q5 sẽ là 1 tuple không chỉ lưu vị trí của nó mà còn cả vị trí các góc mà chưa đến.
    + Hàm getStartState ngoài trả về vị trí bắt đầu sẽ trả về 1 tuple gồm 2 phần tử: vị trí bắt đầu và một tuple khác gồm vị trí 4 góc.
    + Hàm isGoalState sẽ trả về true nếu tại state đó độ dài của tuple lưu vị trí các góc chưa tới bằng 0 tức là đã đi tới cả 4 góc.
    + Hàm getSuccesors lúc này sẽ phải trả về được vị trí của trạng thái tiếp theo, hành động để đi đến trạng thái đó, đồng thời là các góc mà trạng thái đó chưa tới. Nếu trạng thái này là 1 góc thì góc hiện tại sẽ không được thêm vào tuple các góc chưa tới nữa. Vì thế ở những trạng thái sau cũng sẽ không còn góc này nữa.
- Question 6:
    + Hàm cornerHeuristic sẽ tính khoảng cách từ vị trí hiện tại đến từng góc chưa tới và sẽ trả về khoảng cách tới góc xa nhất.
