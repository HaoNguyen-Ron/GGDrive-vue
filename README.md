# Hello World

1 packing version có 3 chữ số (eg: node -v: 20.11.1)
    Số 1: 1 Breaking Change;
    Số 2: Feature Change;
    Số 3: Patch;

Mọi ngôn ngữ đều có file lock.

1 file .lock của package manager giúp giữ nguyên version của một dependencies của 1 package dù package đó đã đc patch. Điều này giúp tránh xung đột các dependency với nhau.