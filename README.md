#include <stdio.h>
#include <conio.h>
#include <graphics.h>
#include <stdlib.h>
#include <windows.h>
#include <time.h>

#define CLOUD_COUNT 5
#define BIRD_COUNT 3
#define FLOWER_COUNT 10

// Khai báo mảng vị trí đám mây, chim và hoa
long long cloud_positions[CLOUD_COUNT][2];
long long cloud_directions[CLOUD_COUNT];
long long bird_positions[BIRD_COUNT][2];
long long flower_positions[FLOWER_COUNT][2];
long long flower_heights[FLOWER_COUNT];

// Hàm vẽ mặt trời
void sun() {
    setcolor(WHITE);
    setfillstyle(SOLID_FILL, YELLOW);
    pieslice(550, 60, 0, 360, 50);
}

// Hàm vẽ đám mây
void may() {
    setcolor(WHITE);
    setfillstyle(SOLID_FILL, WHITE);
    for (int k = 0; k < CLOUD_COUNT; k++) {
        fillellipse(cloud_positions[k][0], cloud_positions[k][1], 50, 40);
        fillellipse(cloud_positions[k][0] + 50, cloud_positions[k][1], 40, 30);
        fillellipse(cloud_positions[k][0] - 50, cloud_positions[k][1], 40, 30);
        fillellipse(cloud_positions[k][0] + 30, cloud_positions[k][1] - 20, 40, 30);
        fillellipse(cloud_positions[k][0] - 30, cloud_positions[k][1] - 20, 40, 30);
    }
}

// Hàm vẽ chim
void draw_birds() {
    setcolor(RED);
    for (int k = 0; k < BIRD_COUNT; k++) {
        circle(bird_positions[k][0], bird_positions[k][1], 10); // Đầu chim
        line(bird_positions[k][0] - 10, bird_positions[k][1], bird_positions[k][0] + 10, bird_positions[k][1]); // Cánh
        bird_positions[k][0] += 5; // Di chuyển chim sang phải
        if (bird_positions[k][0] > getmaxx()) { // Nếu ra ngoài màn hình
            bird_positions[k][0] = -10; // Quay lại bên trái
            bird_positions[k][1] = rand() % 200 + 50; // Thay đổi vị trí Y ngẫu nhiên
        }
    }
}

// Hàm vẽ hoa
void draw_flowers() {
    setcolor(MAGENTA);
    for (int k = 0; k < FLOWER_COUNT; k++) {
        circle(flower_positions[k][0], 400 + flower_heights[k], 5); // Đầu hoa
        line(flower_positions[k][0], 405 + flower_heights[k], flower_positions[k][0], 410 + flower_heights[k]); // Thân hoa

        // Tạo hiệu ứng nở hoa
        flower_heights[k] = (flower_heights[k] + 1) % 10; // Tăng chiều cao để tạo hiệu ứng nhẹ
    }
}

// Hàm vẽ đường và cảnh vật
void duong() {
    setfillstyle(1, LIGHTGREEN);
    bar(0, 450, 800, 500);
    setfillstyle(1, LIGHTGRAY);
    bar(0, 350, 800, 450);
    
    // Vẽ cây cối
    setfillstyle(SOLID_FILL, GREEN);
    for (int x = 100; x < 800; x += 150) {
        bar(x, 400, x + 20, 450); // Thân cây
        circle(x + 10, 370, 30); // Tán cây
    }
}

// Hàm vẽ nhân vật
void draw_character(long long i, long long j, long long m) {
    setcolor(WHITE);
    circle(50 + i, 300 + j, 15);  // Đầu
    line(50 + i, 315 + j, 50 + i, 350 + j);  // Thân
    line(50 + i, 330 + j, 20 + i, 320 + j);  // Tay trái
    line(50 + i, 330 + j, 80 + i, 320 + j);  // Tay phải
#include <stdio.h>
#include <conio.h>
#include <graphics.h>
#include <stdlib.h>
#include <windows.h>
#include <time.h>

#define CLOUD_COUNT 5
#define BIRD_COUNT 3
#define FLOWER_COUNT 10

// Khai báo mảng vị trí đám mây, chim và hoa
long long cloud_positions[CLOUD_COUNT][2];
long long cloud_directions[CLOUD_COUNT];
long long bird_positions[BIRD_COUNT][2];
long long flower_positions[FLOWER_COUNT][2];
long long flower_heights[FLOWER_COUNT];

// Hàm vẽ mặt trời
void sun() {
    setcolor(WHITE);
    setfillstyle(SOLID_FILL, YELLOW);
    pieslice(550, 60, 0, 360, 50);
}

// Hàm vẽ đám mây
void may() {
    setcolor(WHITE);
    setfillstyle(SOLID_FILL, WHITE);
    for (int k = 0; k < CLOUD_COUNT; k++) {
        fillellipse(cloud_positions[k][0], cloud_positions[k][1], 50, 40);
        fillellipse(cloud_positions[k][0] + 50, cloud_positions[k][1], 40, 30);
        fillellipse(cloud_positions[k][0] - 50, cloud_positions[k][1], 40, 30);
        fillellipse(cloud_positions[k][0] + 30, cloud_positions[k][1] - 20, 40, 30);
        fillellipse(cloud_positions[k][0] - 30, cloud_positions[k][1] - 20, 40, 30);
    }
}

// Hàm vẽ chim
void draw_birds() {
    setcolor(RED);
    for (int k = 0; k < BIRD_COUNT; k++) {
        circle(bird_positions[k][0], bird_positions[k][1], 10); // Đầu chim
        line(bird_positions[k][0] - 10, bird_positions[k][1], bird_positions[k][0] + 10, bird_positions[k][1]); // Cánh
        bird_positions[k][0] += 5; // Di chuyển chim sang phải
        if (bird_positions[k][0] > getmaxx()) { // Nếu ra ngoài màn hình
            bird_positions[k][0] = -10; // Quay lại bên trái
            bird_positions[k][1] = rand() % 200 + 50; // Thay đổi vị trí Y ngẫu nhiên
        }
    }
}

// Hàm vẽ hoa
void draw_flowers() {
    setcolor(MAGENTA);
    for (int k = 0; k < FLOWER_COUNT; k++) {
        circle(flower_positions[k][0], 400 + flower_heights[k], 5); // Đầu hoa
        line(flower_positions[k][0], 405 + flower_heights[k], flower_positions[k][0], 410 + flower_heights[k]); // Thân hoa

        // Tạo hiệu ứng nở hoa
        flower_heights[k] = (flower_heights[k] + 1) % 10; // Tăng chiều cao để tạo hiệu ứng nhẹ
    }
}

// Hàm vẽ đường và cảnh vật
void duong() {
    setfillstyle(1, LIGHTGREEN);
    bar(0, 450, 800, 500);
    setfillstyle(1, LIGHTGRAY);
    bar(0, 350, 800, 450);
    
    // Vẽ cây cối
    setfillstyle(SOLID_FILL, GREEN);
    for (int x = 100; x < 800; x += 150) {
        bar(x, 400, x + 20, 450); // Thân cây
        circle(x + 10, 370, 30); // Tán cây
    }
}

// Hàm vẽ nhân vật
void draw_character(long long i, long long j, long long m) {
    setcolor(WHITE);
    circle(50 + i, 300 + j, 15);  // Đầu
    line(50 + i, 315 + j, 50 + i, 350 + j);  // Thân
    line(50 + i, 330 + j, 20 + i, 320 + j);  // Tay trái
    line(50 + i, 330 + j, 80 + i, 320 + j);  // Tay phải
// Chân
    if (m % 2 == 0) {
        line(50 + i, 350 + j, 50 + i, 390 + j);  // Chân thẳng
    } else {
        line(50 + i, 350 + j, 35 + i, 390 + j);  // Chân trái
        line(50 + i, 350 + j, 65 + i, 390 + j);  // Chân phải
    }
}

int main() {
    int driver = 0, mode = 0, maloi;
    initgraph(&driver, &mode, (char*)"");
    if ((maloi = graphresult()) != 0) {
        printf("Không thể khởi động đồ họa \n");
        printf("Mã lỗi : %d \n%s ", maloi, grapherrormsg(maloi));
        getch();
        exit(1);
    }

    srand(time(NULL)); // Khởi tạo seed cho random
    // Khởi tạo vị trí và hướng chuyển động cho đám mây, chim và hoa
    for (int k = 0; k < CLOUD_COUNT; k++) {
        cloud_positions[k][0] = 100 + rand() % 600; // Vị trí X
        cloud_positions[k][1] = 70 + rand() % 100;  // Vị trí Y
        cloud_directions[k] = (rand() % 2) * 2 - 1; // -1 hoặc 1
    }
    for (int k = 0; k < BIRD_COUNT; k++) {
        bird_positions[k][0] = -10; // Bắt đầu bên trái
        bird_positions[k][1] = rand() % 200 + 50; // Vị trí Y ngẫu nhiên
    }
    for (int k = 0; k < FLOWER_COUNT; k++) {
        flower_positions[k][0] = 50 + k * 70; // Vị trí X
        flower_heights[k] = rand() % 10; // Chiều cao hoa ngẫu nhiên
    }

    long long i = 0, j = 0, m = 1, page = 0;
    long long max_width = getmaxx(); // Lấy giới hạn chiều rộng của màn hình

    while (1) {
        setactivepage(page);
        cleardevice(); // Xóa trang active trước khi vẽ

        setbkcolor(LIGHTBLUE);
        sun();
        may();
        duong();
        draw_birds(); // Vẽ chim
        draw_flowers(); // Vẽ hoa
        draw_character(i, j, m); // Vẽ nhân vật

        // Di chuyển nhân vật theo phím
        if (GetAsyncKeyState(VK_LEFT)) {
            if (i > -40) { // Giới hạn bên trái
                i -= 5;
                m++;
            }
        }
        if (GetAsyncKeyState(VK_RIGHT)) {
            if (i < max_width - 50) { // Giới hạn bên phải
                i += 5;
                m++;
            }
        }
        if (GetAsyncKeyState(VK_ESCAPE)) { // Thoát bằng phím ESC
            break;
        }
        if (GetAsyncKeyState(VK_UP)) { // Di chuyển lên
            j -= 5;
        }
        if (GetAsyncKeyState(VK_DOWN)) { // Di chuyển xuống
            j += 5;
        }

        // Cập nhật vị trí đám mây
        for (int k = 0; k < CLOUD_COUNT; k++) {
            cloud_positions[k][0] += 1; // Di chuyển đám mây sang phải
            cloud_positions[k][1] += cloud_directions[k]; // Di chuyển đám mây lên/xuống
            if (cloud_positions[k][0] > max_width) { // Nếu ra ngoài
                cloud_positions[k][0] = -100; // Quay lại bên trái
                cloud_positions[k][1] = 70 + rand() % 100; // Thay đổi vị trí Y ngẫu nhiên
cloud_directions[k] = (rand() % 3) - 1; // Hướng di chuyển
            }

            // Đảm bảo đám mây không ra ngoài màn hình theo chiều dọc
            if (cloud_positions[k][1] < 0 || cloud_positions[k][1] > 400) {
                cloud_directions[k] *= -1; // Đảo chiều nếu ra ngoài
            }
        }

        setvisualpage(page); // Hiển thị trang hiện tại
        page = 1 - page; // Chuyển đổi giữa 2 trang

        delay(30); // Giảm độ trễ để chuyển trang mượt mà hơn
    }

    closegraph();
    return 0;
}
