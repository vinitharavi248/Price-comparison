# Price-comparison
#include <stdio.h>
#include <string.h>
float get_zomato_price(const char* food_item) {
    if (strcmp(food_item,"Pizza") == 0) {
        return 250.00;
    } else if (strcmp(food_item,"Burger") == 0) {
        return 120.00;
    } else if (strcmp(food_item,"Pasta") == 0) {
        return 180.00;
    }
    else if (strcmp(food_item,"Sushi") == 0) {
        return 280.00;
        }
        else if (strcmp(food_item,"Idly") == 0) {
        return 50.00;
        }
        else {
        return -1.0; 
    }
}
float get_swiggy_price(const char* food_item) {
    if (strcmp(food_item,"Pizza") == 0) {
        return 230.00;
    } else if (strcmp(food_item,"Burger") == 0) {
        return 110.00;
    } else if (strcmp(food_item,"Pasta") == 0) {
        return 190.00;
    } 
    else if (strcmp(food_item,"Sushi") == 0) {
        return 280.00;
        }
        else if (strcmp(food_item,"Idly") == 0) {
        return 80.00;
        }
    else {
        return -1.0; 
    }
}
void compare_prices(float zomato_price, float swiggy_price) {
    if (zomato_price < swiggy_price) {
        printf("Zomato is cheaper: Rs %.2f\n", zomato_price);
    } else if (swiggy_price < zomato_price) {
        printf("Swiggy is cheaper: Rs %.2f\n", swiggy_price);
    } else {
        printf("Both Zomato and Swiggy have the same price: Rs %.2f\n", zomato_price);
    }
}

int main() {
    char food_item[50];
     printf("\n");
    printf(".........MENU...........\n");
    printf("Pizza\nBurger\nPasta\nSushi\nIdly\n");
    printf("\n");
    printf("Enter the food item to compare prices : ");
    scanf(" %s",food_item);
    float zomato_price = get_zomato_price(food_item);
    float swiggy_price = get_swiggy_price(food_item);
    if (zomato_price == -1.0) {
        printf("Food item not found on Zomato.\n");
    } else if (swiggy_price == -1.0) {
        printf("Food item not found on Swiggy.\n");
    } else {
        printf("Zomato price for %s: Rs %.2f\n", food_item, zomato_price);
        printf("Swiggy price for %s: Rs %.2f\n", food_item, swiggy_price);
 compare_prices(zomato_price, swiggy_price);
    }
 return 0;
}
