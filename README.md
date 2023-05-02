#include <stdio.h>
#include <string.h>

int main() {
    char type[10];
    float price, extra, total, discount, gst, net;

    // read input from user
    printf("Enter car type (Hatchback/Sedan/SUV/MUV): ");
    scanf("%s", type);
    printf("Enter car price: ");
    scanf("%f", &price);
    printf("Enter extra fitting price: ");
    scanf("%f", &extra);

    // calculate net amount
    total = price + extra;
    if (strcmp(type, "Hatchback") == 0) {
        discount = total * 0.03;
    } else if (strcmp(type, "Sedan") == 0) {
        discount = total * 0.05;
    } else if (strcmp(type, "SUV") == 0) {
        discount = total * 0.10;
    } else if (strcmp(type, "MUV") == 0) {
        discount = total * 0.15;
    } else {
        printf("Invalid Type\n");
        return 0;
    }
    gst = (total - discount) * 0.12;
    net = total - discount + gst;

    // display result
    printf("Net amount to be paid: %.2f\n", net);

    return 0;
}
