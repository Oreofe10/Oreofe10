using System;
using System.Data.SqlClient;

namespace LoanEligibilityChecker
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Loan Eligibility Checker");

            Console.Write("Enter Name: ");
            string name = Console.ReadLine();

            Console.Write("Enter Age: ");
            int age = int.Parse(Console.ReadLine());

            Console.Write("Enter Income: ");
            double income = double.Parse(Console.ReadLine());

            bool isEligible = CheckEligibility(age, income);

            if (isEligible)
            {
                Console.WriteLine("Applicant is eligible for a loan.");
            }
            else
            {
                Console.WriteLine("Applicant is not eligible for a loan.");
            }

            SaveApplicantDetails(name, age, income);
        }

        private static bool CheckEligibility(int age, double income)
        {
            // Sample criteria: Age between 18 and 65, income above $30,000
            if (age >= 18 && age <= 65 && income > 30000)
            {
                return true;
            }
            return false;
        }
