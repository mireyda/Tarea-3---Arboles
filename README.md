/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 */

package com.mycompany.estructurasdedatos_2;
import javax.swing.JOptionPane;

/**
 *
 * @author mirey
 */
public class Estructurasdedatos_2 {

    public static void main(String[] args) {
       int dato;
       int opcion=0;
       arbolbinario binario=new arbolbinario();
       do{
           try{
                opcion = Integer.parseInt(JOptionPane.showInputDialog(null,
                   "1. Agregar nodo \n"+
                   "2. buscar el valor menor\n"+
                   "3. buscar el valor mayor\n"+
                   "4. salir\n"+
                   "***Elige una opcion***", JOptionPane.QUESTION_MESSAGE));
          switch(opcion){
           case 1:
                    dato= Integer.parseInt(JOptionPane.showInputDialog(null,
                      "ingrese el nodo","agregar nodo",JOptionPane.QUESTION_MESSAGE));
                      binario.insertarnodo(dato,binario.getraiz());
            break;
            
           case 2:
               if(!binario.estavacio()){
                   System.out.print("\nel menor valor es: "+binario.buscarmenor());
                   System.out.print("\n--------------------------------------------"); 
               }else{
                   JOptionPane.showInputDialog(null,"ARBOL VACIO","INSERT NODO",
                           JOptionPane.WARNING_MESSAGE);                   
               }               
            break;
            case 3:
                if(!binario.estavacio()){
                   System.out.print("\nel mayor valor es: "+binario.buscarmayor());
                   System.out.print("\n--------------------------------------------"); 
               }else{
                   JOptionPane.showInputDialog(null,"ARBOL VACIO","INSERT NODO",
                           JOptionPane.WARNING_MESSAGE);                   
               }       
            break;            
            
           case 4:
                    JOptionPane.showMessageDialog(null,"finalizado","fin",JOptionPane.INFORMATION_MESSAGE);     
             break;
           default:
                    JOptionPane.showMessageDialog(null,"NO HAY ESA OPCION","Eliga una opcion existetnte",JOptionPane.ERROR_MESSAGE);
            }               
           }catch(NumberFormatException error){
               JOptionPane.showMessageDialog(null,"Error"+error.getMessage());
           }
       }while (opcion!=4);
    }
}
