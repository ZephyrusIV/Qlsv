public static void main(String[] args) {
              // Cấu hình thông tin SQL Server
        String url = "jdbc:sqlserver://localhost:1433;databaseName=QLSV;encrypt=false";
        String user = "sa";
        String password = "123";
        // Kết nối đến SQL Server
        try (Connection conn = DriverManager.getConnection(url, user, password)) {
            System.out.println("Ket noi thanh cong SQL Server!");
            // Tạo statement để truy vấn dữ liệu
            Statement stmt = conn.createStatement();
            ResultSet rs = stmt.executeQuery("SELECT * FROM SV");
            // Hiển thị dữ liệu
            while (rs.next()) {
                System.out.println("Mã SV: " + rs.getString("MASV") + ", Họ tên: " + rs.getString("HOTEN"));

            }

        } catch (SQLException e) {
            System.out.println(" Loi ket noi: " + e.getMessage());
        }
    }
