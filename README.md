# GameOfLife
import processing.core.PApplet;

public class Main_GoL extends PApplet {

	public static void main(String[] args) {
		
		PApplet.main("Main_GoL");
	
	}
	
	int square_size = 8, width = 50 , height = 50;
	Estructura_GoL gol = new Estructura_GoL(width , height);
	
	public void settings() {
		
		  size(width * square_size , height * square_size);
		  
		}

		public void draw() {
			
		  background(50);
		  
		  for(int i = 0 ; i< height ; i++)
		  {
			  for(int j = 0; j < width; j++)
			  {
				  if(gol.Cellular_automata[i][j] == 1)
				  
					  fill(255,0,0);
				  else
					  fill(0);
				  
				  rect(j*square_size , i * square_size , square_size , square_size);
				  
				  
			  }
				  
			  try
			  {
				  
				  Thread.sleep(10);
				  gol.nextIteration();
				  
			  }catch(Exception e){e.printStackTrace();}
			 
		  }
		  
		}
	
	}
