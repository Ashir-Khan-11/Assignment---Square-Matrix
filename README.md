# Assignment---Square-Matrix

/* Write Java program that takes input dimension of a square matrix, then take input all the elements of the matrix.
Your program should calculate sum of all the elements in each of the row and in each of the column,
moreover it should also display the sum of all the diagonal elements and then sum all reverse diagonal elements.*/

import java.util.Scanner;

public class SquareMatrix {
    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        int matrixSize;

        System.out.print("Enter size of square matrix: ");
        matrixSize = sc.nextInt();

        int[][] matrix = new int[matrixSize][matrixSize];

        System.out.println("Enter elements:");
        for (int row = 0; row < matrixSize; row = row + 1) {
            for (int column = 0; column < matrixSize; column = column + 1) {
                matrix[row][column] = sc.nextInt();
            }
        }

        System.out.println("Matrix:");
        for (int row = 0; row < matrixSize; row = row + 1) {
            for (int column = 0; column < matrixSize; column = column + 1) {
                System.out.print(matrix[row][column] + " ");
            }
            System.out.println();
        }

        System.out.println("Row sums:");
        for (int row = 0; row < matrixSize; row = row + 1) {
            int rowSum = 0;
            for (int column = 0; column < matrixSize; column = column + 1) {
                rowSum = rowSum + matrix[row][column];
            }
            System.out.println(rowSum);
        }

        System.out.println("Column sums:");
        for (int column = 0; column < matrixSize; column = column + 1) {
            int columnSum = 0;
            for (int row = 0; row < matrixSize; row = row + 1) {
                columnSum = columnSum + matrix[row][column];
            }
            System.out.println(columnSum);
        }

        int forwardDiagonalSum = 0;
        for (int row = 0; row < matrixSize; row = row + 1) {
            forwardDiagonalSum = forwardDiagonalSum + matrix[row][row];
        }
        System.out.println("Forward diagonal sum = " + forwardDiagonalSum);

        int reverseDiagonalSum = 0;
        for (int row = 0; row < matrixSize; row = row + 1) {
            reverseDiagonalSum = reverseDiagonalSum + matrix[row][matrixSize - 1 - row];
        }
        System.out.println("Reverse diagonal sum = " + reverseDiagonalSum);

    }
}
