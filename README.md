#include <stdio.h>

int main() {
    float currentCGPA, targetCGPA, requiredSGPA;
    int currentCredits, upcomingCredits;

    printf("=========================================\n");
    printf("   Target CGPA Forecaster (Banasthali)   \n");
    printf("=========================================\n\n");

    // 1. Gather current academic standing
    printf("Enter your current CGPA (e.g., 8.12): ");
    scanf("%f", &currentCGPA);

    printf("Enter total credits completed so far (e.g., 60): ");
    scanf("%d", &currentCredits);

    // 2. Gather future goals
    printf("Enter your Dream Target CGPA: ");
    scanf("%f", &targetCGPA);

    printf("Enter total credits for the upcoming semester: ");
    scanf("%d", &upcomingCredits);

    // 3. The Math (Calculating points)
    float totalCurrentPoints = currentCGPA * currentCredits;
    float totalTargetPoints = targetCGPA * (currentCredits + upcomingCredits);
    float requiredPoints = totalTargetPoints - totalCurrentPoints;
    
    // Calculate what they actually need this semester
    requiredSGPA = requiredPoints / upcomingCredits;

    // 4. Output the Real-World Advice
    printf("\n=========================================\n");
    printf("             FORECAST RESULT             \n");
    printf("=========================================\n");

    if (requiredSGPA > 10.0) {
        printf("Status: Mathematically Impossible! \n");
        printf("You need an SGPA of %.2f this semester, which exceeds 10.0.\n", requiredSGPA);
        printf("Advice: Lower your target CGPA or spread the recovery over multiple semesters.\n");
    } else if (requiredSGPA <= 0.0) {
        printf("Status: Goal Already Secured! \n");
        printf("Even with a very low score, your past credits will keep you above %.2f.\n", targetCGPA);
    } else {
        printf("Status: Achievable! \n");
        printf("You need to score an SGPA of %.2f this semester to hit your target of %.2f.\n", requiredSGPA, targetCGPA);
    }
    printf("=========================================\n");

    return 0;
}
