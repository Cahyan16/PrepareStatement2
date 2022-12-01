package preparestatement;

import java.sql.Connection;
import java.sql.PreparedStatement;
import java.sql.SQLDataException;
import java.sql.SQLException;

public class DatabaseServicesUtilities {
    public static void main(String[] args) {
    Connection koneksi = KoneksiDatabase.getKoneksi();{    
    PreparedStatement prepare = null;
    try{
        String sql="SELECT * FROM barang";
        prepare = koneksi.prepareStatement(sql);
        System.out.println("Prepare statement berhasil dibuat");
    }catch(SQLException ex){
        System.out.println("Prepare statement gagal dibuat");
        System.out.println("Pesan : "+ex.getMessage());
    }finally{
        if (prepare != null){
            try{
                prepare.close();
                System.out.println("Prepare statement berhasil ditutup");
            }catch(SQLException ex){
                System.out.println("Pesan : "+ex.getMessage());   
            }
        }
    }
    }
    }
}


