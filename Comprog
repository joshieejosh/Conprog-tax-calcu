package projectcomprog;

import javax.swing.JOptionPane;

public class TAXCALCU2 {

    public static void main(String[] args) {
        final int MAX_ENTRIES = 5;
        double[] salaries = new double[MAX_ENTRIES];
        double[] taxes = new double[MAX_ENTRIES];
        int count = 0;
        boolean running = true;

        while (running && count < MAX_ENTRIES) {
            String input = JOptionPane.showInputDialog("Enter salary #" + (count + 1) + ":");
            double salary = Double.parseDouble(input);

            salaries[count] = salary;
            taxes[count] = calculateTax(salary);
            count++;

            String[] options = {"Add Another", "Show Results", "Exit"};
            int choice = JOptionPane.showOptionDialog(null, "Choose an action:", "Options",
                    JOptionPane.DEFAULT_OPTION, JOptionPane.INFORMATION_MESSAGE, null, options, options[0]);

            switch (choice) {
                case 0:
                    if (count == MAX_ENTRIES) {
                        JOptionPane.showMessageDialog(null, "Maximum number of entries reached.");
                    }
                    break;
                case 1:
                    showResults(salaries, taxes, count);
                    break;
                case 2:
                default:
                    running = false;
                    break;
            }
        }

        JOptionPane.showMessageDialog(null, "Thank you for using!");
    }
    public static double calculateTax(double salary) {
        double tax;

        if (salary <= 250000) {
            // No tax for annual salary up to ₱250,000
            tax = 0;
        } else if (salary <= 400000) {
            // 15% tax on the amount over ₱250,000
            tax = (salary - 250000) * 0.15;
        } else if (salary <= 800000) {
            // ₱22,500 plus 20% of the amount over ₱400,000
            tax = (salary - 400000) * 0.20 + 22500;
        } else if (salary <= 2000000) {
            // ₱102,500 plus 25% of the amount over ₱800,000
            tax = (salary - 800000) * 0.25 + 102500;
        } else if (salary <= 8000000) {
            // ₱402,500 plus 30% of the amount over ₱2,000,000
            tax = (salary - 2000000) * 0.30 + 402500;
        } else {
            // ₱2,202,500 plus 35% of the amount over ₱8,000,000
            tax = (salary - 8000000) * 0.35 + 2202500;
        }

        return tax;
    }

    public static void showResults(double[] salaries, double[] taxes, int count) {
        StringBuilder message = new StringBuilder("Salary and Tax Summary:\n");

        for (int i = 0; i < count; i++) {
            String line = String.format("Salary %d: ₱%.2f -> Tax: ₱%.2f\n", i + 1, salaries[i], taxes[i]);
            message.append(line);
        }

        JOptionPane.showMessageDialog(null, message.toString());
    }



	}


