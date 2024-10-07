Cinema seat booking code
import java.util.Scanner;
public class CinemaBooking{
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int rows = 5;
        int seatsPerRow = 6;
        int[][] cinemaHall = new int[rows][seatsPerRow];
        while (true) {
            System.out.println("\nCurrent Seating Arrangement:");
            displaySeats(cinemaHall);
            System.out.print("\nEnter row number (1 to " + rows + ", or 0 to exit): ");
            int row = scanner.nextInt();
            if (row == 0) {
                System.out.println("Exiting the booking system.");
                break;
            }
            System.out.print("Enter seat number (1 to " + seatsPerRow + "): ");
            int seat = scanner.nextInt();
            if (cinemaHall[row - 1][seat - 1] == 0) {
                cinemaHall[row - 1][seat - 1] = 1;
                System.out.println("Seat successfully booked!");
            } else {
                System.out.println("Sorry, that seat is already booked.");
            }
        }
        scanner.close();
  }
   public static void displaySeats(int[][] cinemaHall) {
        for (int i = 0; i < cinemaHall.length; i++) {
            for (int j = 0; j < cinemaHall[i].length; j++) {
                if (cinemaHall[i][j] == 0) {
                    System.out.print("A ");
                } else {
                    System.out.print("B ");
                }
            }
            System.out.println();
        }
    }
}
