# Java-Desktop

package fito;
import java.sql.*;
import Conexao.Ligar;
import javax.swing.JFileChooser;
import javax.swing.JOptionPane;

public class Login extends javax.swing.JFrame {
Connection conecao;
PreparedStatement pst;
ResultSet rs;

public void logar(){
    String sql ="select * from login where nome_usuario=? and senha = ?";
    try {
        pst = conecao.prepareStatement(sql);
        pst.setString(1, txtUsuario.getText());
        pst.setString(2, txtSenha.getText());
        rs=pst.executeQuery();
        if(rs.next()){
            String se = rs.getString(6);
         String s = rs.getString(8);
        if(se.equals("Administrador")){
        PotenciaTerapeuta potencia = new PotenciaTerapeuta();
        potencia.setVisible(true);
        this.dispose();
        
        
        }
        
        
        }
    } catch (Exception e) {
    }
    
    
    
    
    
}
