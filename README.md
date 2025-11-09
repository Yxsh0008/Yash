# Yash
#include <stdio.h>

int main() {
    int choice;
    float balance = 1000.0; 
    float deposit, withdraw;

    while (1) {
        printf("\n=================================\n");
        printf("          ATM SIMULATOR          \n");
        printf("=================================\n");
        printf("  1. Check Balance\n");
        printf("  2. Deposit Money\n");
        printf("  3. Withdraw Money\n");
        printf("  4. Exit\n");
        printf("=================================\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);

        switch (choice) {

            case 1:
                printf("\n---------------------------------\n");
                printf("  Your Current Balance: Rs %.2f\n", balance);
                printf("---------------------------------\n");
                break;

            case 2:
                printf("\nEnter amount to deposit: Rs ");
                scanf("%f", &deposit);

                if (deposit > 0) {
                    balance += deposit;
                    printf("\n+ Rs %.2f Successfully Deposited!\n", deposit);
                } else {
                    printf("\nInvalid Amount! Please Try Again.\n");
                }
                break;

            case 3:
                printf("\nEnter amount to withdraw: Rs ");
                scanf("%f", &withdraw);

                if (withdraw > 0 && withdraw <= balance) {
                    balance -= withdraw;
                    printf("\n- Rs %.2f Successfully Withdrawn!\n", withdraw);
                } else {
                    printf("\nTransaction Failed! Insufficient Balance or Invalid Amount.\n");
                }
                break;

            case 4:
                printf("\n=================================\n");
                printf("   Thank You for Using the ATM!  \n");
                printf("=================================\n");
                return 0;

            default:
                printf("\nInvalid Choice! Please Enter 1-4.\n");
        }
    }

    return 0;
}
