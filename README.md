# Elonmush
api for elonmu.sh database news about Elon Musk
# main
```cpp
#include "Elonmush.h"
#include <iostream>

int main() {
   Elonmush api;

    auto news = api.random_news().then([](json::value result) {
        std::cout << result.at("source").as_string() << std::endl;
        std::cout << result.at("title").as_string() << std::endl;
        std::cout << result.at("description").as_string() << std::endl;
        std::cout << result.at("url").as_string() << std::endl;
        std::cout << result.at("urlImage").as_string() << std::endl;
        std::cout << result.at("publishDate").as_string() << std::endl;
    });
    news.wait();
    
    return 0;
}
```

# Launch (your script)
```
g++ -std=c++11 -o main main.cpp -lcpprest -lssl -lcrypto -lpthread -lboost_system -lboost_chrono -lboost_thread
./main
```

