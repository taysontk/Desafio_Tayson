import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;

public class DesafioBasis_Tayson {
	
	public int stringLength;
	public int contadorLegth;
	public int c = 0;
	public int cont = 0;
	

	public static void main (String[] args) {   
		boolean resultado = false;
	       //  String de entrada
	       System.out.print("Digite uma entrada: ");   
	  
	       //  Abre o input  
	       BufferedReader br = new BufferedReader(new InputStreamReader(System.in));   
	  
	       String string = null;   
	       DesafioBasis_Tayson f = new DesafioBasis_Tayson();
	       
	       try {	    	   
	    	   string = br.readLine();	    		          
	           resultado = f.balanceador(string);
	       } catch (IOException ioe) {   
	          System.out.println("IO erro tentando ler o nome");   
	          System.exit(1);   
	       }   
	  
	       System.out.println(" Resultado: " + resultado);   
	  
	    }
	
	
	public boolean balanceador(String string){
			
		if(c == 0){
		stringLength = string.length();
		contadorLegth = 0;
		c++;
		}
		
		char caracter = string.charAt(contadorLegth);
		String x = String.valueOf(caracter);
		
		if(stringLength == 0){
			if(cont == 0){
				return true;
			}else{
				return false;
			}
		}else{
			if("(".equals(x)){
				cont ++;
				
			}else if(")".equals(x)){
				cont--;
			}
			stringLength--;
			if(contadorLegth != string.length()-1){
			contadorLegth++;
			}			
		}		
		return balanceador(string);		
	}
	

}
