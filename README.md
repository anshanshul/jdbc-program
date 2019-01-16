# jdbc-program

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.SQLException;
import java.sql.Statement;
public class Poi {
   

   public static  void main(String args[]){
       Statement stmt=null;
   try{
       Class.forName("com.mysql.jdbc.Driver");
       try (Connection con = DriverManager.getConnection("jdbc:sqlserver://localhost:3306/login_id", "sa", "root")){ 
       
           stmt = con.createStatement();
           stmt.executeUpdate("insert into login values('sumit',123456)");
           stmt.executeUpdate("insert into0 login values ('xsys','projects')");
           con.commit();
       }
       ResultSet rs= stmt.executeQuery("select*from login");
     while(true) {
         if (!rs.next()) break;

         String i1 = rs.getString(1);
   String i2 = rs.getString(2);
   System.out.println("uid:" +i1+" pwd:" +i2);



}

   } catch (ClassNotFoundException e) {
       e.printStackTrace();
   } catch (SQLException e) {
       e.printStackTrace();
   }
   }


}
