Write a C program for the following scenario: A telecom service provider offers
recharge discount of Rs. 100 for using GPay wallet, Rs. 50 for using Phone Pe
wallet and Rs. 200 for using Axis Bank credit card only if in all cases the recharge
amount is more than Rs. 499. Program must accept the Recharge amount and
mode of payment. The net amount to be paid must be the output of the program.

#include <stdio.h>

int main() {
    float recharge_amount;
    char payment_mode;

    // Input recharge amount and payment mode
    printf("Enter the recharge amount: ");
    scanf("%f", &recharge_amount);
    printf("Enter the payment mode (G for GPay, P for Phone Pe, A for Axis Bank credit card): ");
    scanf(" %c", &payment_mode);

    // Calculate net amount to be paid
    float discount = 0;
    if (recharge_amount > 499) {
        switch(payment_mode) {
            case 'G':
                discount = 100;
                break;
            case 'P':
                discount = 50;
                break;
            case 'A':
                discount = 200;
                break;
            default:
                printf("Invalid payment mode.\n");
                return 1;
        }
    }

    float net_amount = recharge_amount - discount;

    // Check if net amount is negative
    if (net_amount < 0) {
        printf("Invalid recharge amount. Recharge amount must be more than Rs. 499.\n");
        return 1;
    }

    printf("Net amount to be paid: Rs. %.2f\n", net_amount);

    return 0;
}
