package qlsv1;
import java.sql.*;
public class QLSV1 {

    public static void main(String[] args) {
        String url = "jdbc:sqlserver://localhost:1433;databaseName=QLSV;encrypt=false";
        String user = "sa";
        String password = "123";
        try (Connection conn = DriverManager.getConnection(url, user, password)) {
            System.out.println("Ket noi thanh cong SQL Server!");
            Statement stmt = conn.createStatement();
            ResultSet rs = stmt.executeQuery("SELECT * FROM SV ");
            while (rs.next()) {
                System.out.println("Mã SV: " + rs.getString("MASV") + ", Họ tên: " + rs.getString("HOTEN"));
            }
        } catch (SQLException e) {
            System.out.println(" Loi ket noi: " + e.getMessage());
        }
    }
}
