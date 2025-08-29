# PAY-ROLL-SCRIPT
C COMPILER PAY ROLL SCRIPT
//START HERE
#include <stdio.h>

int main() {
    // Declare variables
    char name[50];
    char position[50];
    float rate, hoursWorked;
    float grossPay, pagibig, sss, tax, totalDeduction, netPay;

    printf("Enter NAME: ");
    scanf("%s", name);

    printf("Enter POSITION: ");
    scanf("%s", position);

    while (1) {
        printf("Enter RATE [65 - 600]: ");
        scanf("%f", &rate);

        if (rate >= 65 && rate <= 600) {
            break;
        } else {
            printf("Invalid rate! It must be between 65 and 600. Please try again.\n");
        }
    }

    printf("Enter Number of hours worked: ");
    scanf("%f", &hoursWorked);

    grossPay = rate * hoursWorked;

    // PAGIBIG: 3% of gross
    pagibig = grossPay * 0.03;

    // SSS based on grossPay using if-else
    if (grossPay < 5000) {
        sss = 350.00;
    } else if (grossPay <= 7000) {
        sss = 400.00;
    } else if (grossPay <= 9000) {
        sss = 450.00;
    } else if (grossPay <= 11000) {
        sss = 500.00;
    } else if (grossPay <= 13000) {
        sss = 550.00;
    } else {
        sss = 600.00;
    }

    // TAX: 2% of gross
    tax = grossPay * 0.02;

    totalDeduction = pagibig + sss + tax;
    netPay = grossPay - totalDeduction;

    printf("\n--- PAYSLIP ROLL ---\n");
    printf("Name: %s\n", name);
    printf("Position: %s\n", position);
    printf("Rate per Hour: %.f\n", rate);
    printf("Number of hours Worked: %.2f\n", hoursWorked);
    printf("Gross Pay: %.f\n", grossPay);
    printf("PAGIBIG: %.f\n", pagibig);
    printf("SSS: %.f\n", sss);
    printf("TAX: %.f\n", tax);
    printf("Total Deduction: %.2f\n", totalDeduction);
    printf("Net Pay: %.f\n", netPay);

    printf("\nProgrammed by RALPH SIMBULAN\n");

    return 0;
}
