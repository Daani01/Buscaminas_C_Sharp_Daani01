Código completo del juego del Busca Minas hecho en la consola de comando de windows. Lenguaje utilizado: C#

------------------------------------


using System;
using System.Collections.Generic;

namespace Space_Invaders
{
   
    class Program
    {
                

        public class NuevaMina
        {

            public int X;

            public int Y;

            

            public NuevaMina()
            {
                               

            }

            public NuevaMina(int pos_X, int pos_Y)
            {

                X = pos_X;

                Y = pos_Y;


                //posicion.x = 3;

            }


            ~NuevaMina()
            {

                

            }

            public void Hola()
            {
                
                //Console.WriteLine("Hola");


            }






        }
        
        
        public class Tablero
        {

            public int[] grid = new int[Altura * Ancho]; //Tamaño del tablero de 400
            
            List<Mina> minas33 = new List<Mina>(); //Guarda el numero de minas

            List<string> NombreJugador = new List<string>(); //Guarda el nombre del jugador



            const int Altura = 20; 
            const int Ancho = 20;  

            const int Hueco = 48;

            static int X = (Ancho / 2);
            static int Y = (Altura / 2);

            
            public int ContadorMinas = 0;
            public int ContadorFallos = 0;


            static bool Jugar = true;
            static bool PonerMina = true;
            static bool Instrucciones = true;
            static bool elegirminas = true;
            static bool NombreJugadore = true;
            static bool ELMEGA10 = true;


            static bool Aporel101 = true; //KK
            static bool Aporel102 = true; //KK
            static bool Aporel103 = true; //KK
            static bool Aporel104 = false; //KK
            static bool super10 = true; //KK


            public Tablero()
            {




            }

            public void Menu()
            {

                while(Instrucciones == true)
                {

                    Console.Write("\n Dime que quieres hacer:\n");
                    Console.Write("\n F1. Jugar\n F2. Controles del juego\n F3. Salir");
                    
                    ConsoleKey key1 = Console.ReadKey(true).Key;

                    Console.Clear();


                    if (key1 == ConsoleKey.F1)
                    {


                        Console.Clear();
                        
                        Instrucciones = false;
                        NombreJugadore = true;

                        Tablero1();
                        Minas();
                        
                        Jugador();



                    } //Activa el juego

                    if (key1 == ConsoleKey.F2)
                    {

                        Console.Clear();
                        Console.Write("El juego consiste en despejar todas las casillas de una pantalla que no oculten una mina." +"\n\n" + "Algunas casillas tienen un número, el cual indica la cantidad de minas que hay en las casillas circundantes.");
                        Console.Write("\n\n");
                        Console.Write("Te mueves por el tablero con las teclas A,W,S,D." + "\n\n" + "Con la tecla C pruebas para destapar la casilla en la que estés y con la V pones una banderilla.");
                        Console.Write("\n\n");
                        Console.Write("Si consigues poner 3 banderas en 3 minas, ganas. Mientras que si pones 3 banderas en otros sitios... perderás.");
                        Console.Write("\n\n");



                    } //Muestra las instrucciones

                    if (key1 == ConsoleKey.F3)
                    {
                        Console.Clear();
                        Instrucciones = false;
                        Jugar = false;
                        elegirminas = false;
                        //Juego = false;

                    } //Cierra el juego



                }


            } //Menu del juego
                        
            public void Tablero1()
            {
                Jugar = true;

                if (Jugar == true)
                {

                    for (int i = 0; i < Altura * Ancho; i++)
                    {


                        if (i >= 0)
                        {

                            grid[i] = Hueco;

                            
                        }

                        

                    }


                }
                
                

                
            } //Inicia el tablero. Todo al valor de Hueco == 48

            public void Pintar()
            {
                
                if (Jugar == true)
                {

                    while (NombreJugadore == true)
                    {
                        //int ContadorGlobal = 5;
                        //Console.Clear();
                        Console.SetCursorPosition((X + 20), (Y + 10));
                        Console.WriteLine("Escribe tu nombre: ");
                        //Console.WriteLine(Nombre);
                        Console.SetCursorPosition((X + 20), (Y + 12));
                        string Nombre = Convert.ToString(Console.ReadLine());

                        NombreJugador.Add(Nombre);
                        NombreJugadore = false;

                        //Console.SetCursorPosition(X, Y);                        
                        //Console.WriteLine("\t\t\tEscribe tu nombre:");
                        //Console.SetCursorPosition((X + 22), (Y + 2));

                        //Console.ReadLine();



                    } //Nombre del jugador
                                        

                    Console.SetCursorPosition(0, 0);

                    
                    for (int i = 0; i < Altura * Ancho; i++)
                    {



                        char letra = Convert.ToChar(grid[i]);
                        //char letra2 = Convert.ToChar(grid[i]);



                        if (grid[i] == 115)//Mina
                        {

                            //Console.Write(" ");




                        }
                        else if (grid[i] == Hueco)
                        {

                            Console.Write("X"); //Final
                            //Console.Write(" "); //Pruebas




                        }

                        if (grid[i] > Hueco)
                        {

                            
                            Console.Write("X"); //Final                            
                            //Console.Write(letra); //Pruebas


                        }

                        
                        


                        if (i % Ancho == 19)
                        {

                            Console.Write("\n");


                        }

                        


                    } //Pintado del tablero



                }
                

            } //Se pregunta el nombre al jugador y se escribe todo el tablero
            
            public void Minas()
            {
                Console.Clear();

                //int Minitas = 0;
                int tamano_lista = 20;
                int eleccionminas;
                if (elegirminas == true)
                {


                    Console.WriteLine("Número de minas pls. Elige entre 5 y 100 minas");

                    //string eleccion = Console.ReadLine();
                    //int r = 40;
                    //int H = 20;
                    //eleccionminas = Int32.TryParse(value, out number);
                    //bool a = Int32.TryParse("5", out r);
                    //readline en 5
                    //string eleccion = Console.ReadLine();
                    string eleccionminasValido = Console.ReadLine();
                    
                    if(Int32.TryParse(eleccionminasValido, out eleccionminas))
                    {

                        //return "Hola";



                    }

                    Console.Clear();

                    
                    if (eleccionminas < 5 || eleccionminas > 100)
                    {

                        Minas(); 
                        elegirminas = true;


                    }

                    if (eleccionminas >= 5 && eleccionminas <= 100)
                    {

                        //Mina mina_aux = new Mina();
                        elegirminas = false;

                        for (int i = 0; i < eleccionminas; i++)
                        {

                            minas33.Add(new Mina()); //GUARDA LAS MINAS DEL ANTERIOR JUEGO
                            //minas33.Add(mina_aux);





                        }


                        if (minas33.Count == tamano_lista)
                        {

                        }





                        if (Jugar == true)
                        {

                            Random aire = new Random();
                            int Mina = 115;


                            //asegurar mina en mismo sitio

                            //Comprobar posiciones

                            for (int j = 0; j < eleccionminas; j++)
                            {

                                PonerMina = true;



                                while (PonerMina == true)
                                {

                                    int X_Mina = aire.Next(Ancho);
                                    int Y_Mina = aire.Next(Altura);

                                    if ((X_Mina > 0) && (X_Mina <= (Ancho - 3)) && (Y_Mina <= (Altura - 2)) && (Y_Mina > 0) && (X_Mina != Mina) && (Y_Mina != Mina))
                                    {

                                        if(grid[X_Mina + Ancho * Y_Mina] != Mina)
                                        {

                                            PonerMina = false;

                                            minas33[j].X = X_Mina;
                                            minas33[j].Y = Y_Mina;

                                            grid[X_Mina + Ancho * Y_Mina] = Mina;

                                            if ((grid[(X_Mina - 1) + Ancho * (Y_Mina - 1)] >= Hueco) && (grid[(X_Mina - 1) + Ancho * (Y_Mina - 1)] != Mina))
                                            {

                                                grid[(minas33[j].X - 1) + Ancho * (minas33[j].Y - 1)] += 1;



                                            }

                                            if ((grid[X_Mina + Ancho * (Y_Mina - 1)] >= Hueco) && (grid[X_Mina + Ancho * (Y_Mina - 1)] != Mina))
                                            {

                                                grid[minas33[j].X + Ancho * (minas33[j].Y - 1)] += 1;



                                            }

                                            if ((grid[(X_Mina + 1) + Ancho * (Y_Mina - 1)] >= Hueco) && (grid[(X_Mina + 1) + Ancho * (Y_Mina - 1)] != Mina))
                                            {

                                                grid[(minas33[j].X + 1) + Ancho * (minas33[j].Y - 1)] += 1;



                                            }

                                            if ((grid[(X_Mina - 1) + Ancho * Y_Mina] >= Hueco) && (grid[(X_Mina - 1) + Ancho * Y_Mina] != Mina))
                                            {

                                                grid[(minas33[j].X - 1) + Ancho * minas33[j].Y] += 1;



                                            }

                                            if ((grid[(X_Mina + 1) + Ancho * Y_Mina] >= Hueco) && (grid[(X_Mina + 1) + Ancho * Y_Mina] != Mina))
                                            {

                                                grid[(minas33[j].X + 1) + Ancho * minas33[j].Y] += 1;




                                            }

                                            if ((grid[(X_Mina - 1) + Ancho * (Y_Mina + 1)] >= Hueco) && (grid[(X_Mina - 1) + Ancho * (Y_Mina + 1)] != Mina))
                                            {

                                                grid[(minas33[j].X - 1) + Ancho * (minas33[j].Y + 1)] += 1;



                                            }

                                            if ((grid[X_Mina + Ancho * (Y_Mina + 1)] >= Hueco) && (grid[X_Mina + Ancho * (Y_Mina + 1)] != Mina))
                                            {

                                                grid[minas33[j].X + Ancho * (minas33[j].Y + 1)] += 1;



                                            }

                                            if ((grid[(X_Mina + 1) + Ancho * (Y_Mina + 1)] >= Hueco) && (grid[(X_Mina + 1) + Ancho * (Y_Mina + 1)] != Mina))
                                            {

                                                grid[(minas33[j].X + 1) + Ancho * (minas33[j].Y + 1)] += 1;



                                            }

                                        }

                                        



                                        




                                    }


                                    //minas33[j] = new Mina();


                                    //minas33[j].X = X_Mina;
                                    //minas33[j].Y = Y_Mina;




                                    if ((minas33[j].X > 0) && (minas33[j].X < (Ancho - 2)) && (minas33[j].Y < (Altura - 2)) && (minas33[j].Y > 0))
                                    {




                                    }






                                }







                            }


                            Pintar();


                        }




                    }




                }




            }  //Se pregunta el número de minas y se posicionan sobre el tablero

            public void Jugador()
            {
                
                if (Jugar == true)
                {
                    
                    
                    const int Num0 = 48;
                    const int Num1 = 49;
                    const int Num2 = 50;
                    const int Num3 = 51;
                    const int Num4 = 52;
                    const int Num5 = 53;
                    const int Num6 = 54;
                    const int Num7 = 55;
                    const int Num8 = 56;
                    const int Num9 = 57;

                    const int Ascii33 = 33;
                    const int Ascii34 = 34;
                    const int Ascii35 = 35;
                    const int Ascii36 = 36;
                    const int Ascii37 = 37;
                    const int Ascii38 = 38;
                    const int Ascii39 = 39;
                    const int Ascii40 = 40;
                    const int Ascii41 = 41;
                    const int Ascii42 = 42;
                    const int Ascii43 = 43;




                    const int NumMina1 = 115;
                    const int NumMinaBandera = 169;
                    const int NumBandera = 184;

                    X = (Ancho / 2);
                    Y = (Altura / 2);

                    Console.SetCursorPosition((X + 20), (Y - 6));
                    Console.WriteLine("Pulsa 'C' para desvelar");

                    Console.SetCursorPosition((X + 20), (Y - 4));
                    Console.WriteLine("Pulsa 'V' para poner una banderilla");


                    Console.SetCursorPosition((X + 20), (Y - 2));
                    Console.WriteLine("Pulsa 'B' para vovler al menú");

                    while (Jugar == true)
                    {

                        Console.SetCursorPosition(X, Y);

                        ConsoleKey key = Console.ReadKey(true).Key;

                        if (key == ConsoleKey.D)
                        {

                            if (X <= (Ancho - 2))
                            {

                                if (grid[(X + 1) + Ancho * Y] == Hueco || grid[(X + 1) + Ancho * Y] >= Hueco || grid[(X + 1) + Ancho * Y] <= Ascii42)
                                {

                                    X += 1;
                                    //grid[X + Ancho * Y] = 79;

                                    //Console.Clear();
                                    //Pintar();
                                    Console.SetCursorPosition(X, Y);




                                }
                                else if (grid[(X + 1) + Ancho * Y] == Hueco)
                                {

                                    X += 1;

                                    //Console.Clear();
                                    //Pintar();
                                    Console.SetCursorPosition(X, Y);

                                }
                                else if (grid[(X + 1) + Ancho * Y] == NumMina1)
                                {


                                    X += 1;

                                    //Console.Clear();
                                    //Pintar();
                                    Console.SetCursorPosition(X, Y);



                                }




                            }



                        } //Mover Derecha

                        if (key == ConsoleKey.A)
                        {

                            if (X > 0)
                            {
                                if (grid[(X - 1) + Ancho * Y] == Hueco || grid[(X - 1) + Ancho * Y] >= Hueco || grid[(X - 1) + Ancho * Y] <= Ascii42)
                                {

                                    X -= 1;
                                    //grid[X + Ancho * Y] = 79;

                                    //Console.Clear();
                                    //Pintar();
                                    Console.SetCursorPosition(X, Y);




                                }
                                else if (grid[(X - 1) + Ancho * Y] == Hueco)
                                {

                                    X -= 1;

                                    //Console.Clear();
                                    //Pintar();
                                    Console.SetCursorPosition(X, Y);


                                }
                                else if (grid[(X - 1) + Ancho * Y] == NumMina1)
                                {

                                    X -= 1;

                                    //Console.Clear();
                                    //Pintar();
                                    Console.SetCursorPosition(X, Y);


                                }



                            }

                        } //Mover Izquierda

                        if (key == ConsoleKey.W)
                        {

                            if (Y > 0)
                            {
                                if (grid[X + Ancho * (Y - 1)] == Hueco || grid[X + Ancho * (Y - 1)] >= Hueco || grid[X + Ancho * (Y - 1)] <= Ascii42)
                                {

                                    Y -= 1;

                                    //Console.Clear();
                                    //Pintar();
                                    Console.SetCursorPosition(X, Y);



                                }
                                else if (grid[X + Ancho * (Y - 1)] == Hueco)
                                {
                                    Y -= 1;

                                    //Console.Clear();
                                    //Pintar();
                                    Console.SetCursorPosition(X, Y);



                                }
                                else if (grid[X + Ancho * (Y - 1)] == NumMina1)
                                {


                                    Y -= 1;

                                    //Console.Clear();
                                    //Pintar();
                                    Console.SetCursorPosition(X, Y);




                                }





                            }



                        } //Mover Arriba

                        if (key == ConsoleKey.S)
                        {

                            if (Y < (Altura - 1))
                            {

                                if (grid[X + Ancho * (Y + 1)] == Hueco || grid[X + Ancho * (Y + 1)] >= Hueco || grid[X + Ancho * (Y + 1)] <= Ascii42)
                                {


                                    Y += 1;

                                    //Console.Clear();
                                    //Pintar();
                                    Console.SetCursorPosition(X, Y);




                                }
                                else if (grid[X + Ancho * (Y + 1)] == Hueco)
                                {
                                    Y += 1;

                                    //Console.Clear();
                                    //Pintar();
                                    Console.SetCursorPosition(X, Y);


                                }
                                else if (grid[X + Ancho * (Y + 1)] == NumMina1)
                                {
                                    Y += 1;

                                    //Console.Clear();
                                    //Pintar();
                                    Console.SetCursorPosition(X, Y);



                                }



                            }


                        } //Mover Abajo

                        if (key == ConsoleKey.C)
                        {

                            super10 = false; // KK

                            while (super10 == true)
                            {
                                if(grid[X + Altura * Y] != Num0)
                                {

                                    super10 = false;
                                    Aporel101 = false;
                                    Aporel102 = false;
                                    Aporel103 = false;
                                    Aporel104 = false;



                                } //Perfecto

                                if (grid[X + Altura * Y] == Num0)
                                {
                                    Aporel101 = true;
                                    Aporel102 = true;
                                    Aporel103 = true;
                                    //Aporel104 = true;


                                    while (Aporel101 == true)
                                    {
                                        if (X <= (Ancho - 1))
                                        {

                                            Console.Write(" ");
                                            X++;

                                            if (grid[X + Altura * Y] != Num0)
                                            {

                                                Aporel101 = false;
                                                super10 = false;


                                            }


                                        }

                                        if (X >= (Ancho - 1))
                                        {

                                            Aporel101 = false;
                                            Console.Write(" ");
                                            super10 = false;




                                        }

                                    }

                                    while (Aporel102 == true)
                                    {
                                        if (X >= 1)
                                        {
                                            X--;
                                            Console.SetCursorPosition(X, Y);

                                            Console.Write(" ");
                                            if(X == 0)
                                            {


                                                //X += 1;


                                            }
                                            else if (grid[(X - 1) + Altura * Y] != Num0)
                                            {

                                                Aporel102 = false;
                                                super10 = false;



                                            }


                                        }

                                        if (X <= 0)
                                        {
                                            super10 = false;

                                            Aporel102 = false;
                                            Console.Write(" ");
                                            Console.SetCursorPosition(X, Y);



                                        }

                                    }

                                    while (Aporel103 == true)
                                    {

                                        if (Y == 0)
                                        {

                                            Aporel103 = false;
                                            Aporel104 = true;
                                            super10 = true;


                                        }

                                        if (Y > 0)
                                        {
                                            Aporel101 = true;
                                            Aporel102 = true;
                                            super10 = true;
                                            Aporel103 = false;
                                            Y--;
                                            Console.SetCursorPosition(X, Y);

                                        }

                                        

                                    }

                                    while(Aporel104 == true)
                                    {

                                        if (Y == 0)
                                        {
                                            Aporel101 = true;
                                            Aporel102 = true;
                                            //super10 = true;
                                            Aporel104 = false;
                                            Aporel103 = false;

                                            Y++;
                                            Console.SetCursorPosition(X, Y);

                                        }

                                        if(Y == Altura)
                                        {

                                            Aporel104 = false;
                                            //Aporel103 = true;

                                        }
                                    }
                                    //Console.SetCursorPosition((X - 5), (Y - 5));

                                }


                            } // KK







                            if (grid[X + Altura * Y] == Num0)
                            {
                                int Xdel10 = 0;
                                int Ydel10 = 0;

                                while(ELMEGA10 == true)
                                {

                                    Console.SetCursorPosition(Xdel10, Ydel10);

                                    for (int El10 = 0; El10 < Altura * Ancho; El10++)
                                    {


                                        if (grid[El10] == Num0)
                                        {

                                            Console.Write(" ");
                                            
                                        }



                                        if (grid[El10] >= Num1 && grid[El10] <= Num9)
                                        {
                                            
                                            Console.Write("X"); // QUE NO SE ESCRIBA NADA DE NADA
                                            
                                        }


                                        if(grid[El10] == NumMina1)
                                        {


                                            Console.Write("X");


                                        }


                                        if (grid[El10] == Ascii34)
                                        {

                                            Console.Write("1");


                                        }

                                        if(grid[El10] == Ascii35)
                                        {


                                            Console.Write("2");




                                        }

                                        if (grid[El10] == Ascii36)
                                        {


                                            Console.Write("3");




                                        }

                                        if (grid[El10] == Ascii37)
                                        {


                                            Console.Write("4");




                                        }

                                        if (grid[El10] == Ascii38)
                                        {


                                            Console.Write("5");




                                        }

                                        if (grid[El10] == Ascii39)
                                        {


                                            Console.Write("6");




                                        }

                                        if (grid[El10] == Ascii40)
                                        {


                                            Console.Write("7");




                                        }

                                        if (grid[El10] == Ascii41)
                                        {


                                            Console.Write("8");




                                        }

                                        if (grid[El10] == Ascii42)
                                        {


                                            Console.Write("9");




                                        }

                                        if (grid[El10] == NumBandera)
                                        {


                                            Console.Write("!");




                                        }
                                        if (grid[El10] == NumMinaBandera)
                                        {


                                            Console.Write("@");




                                        }
                                        

                                        if (El10 % Ancho == 19)
                                        {

                                            Console.Write("\n");
                                        }

                                        if (El10 == 20)
                                        {
                                            
                                            Ydel10++;

                                        }


                                    }

                                    ELMEGA10 = false;
                                }

                                


                            }                                                        

                            if (grid[X + Altura * Y] == Num1)
                            {
                                grid[X + Altura * Y] = Ascii34;
                                Console.Write("1");



                            }

                            if (grid[X + Altura * Y] == Num2)
                            {
                                grid[X + Altura * Y] = Ascii35;

                                Console.Write("2");



                            }

                            if (grid[X + Altura * Y] == Num3)
                            {
                                grid[X + Altura * Y] = Ascii36;

                                Console.Write("3");




                            }

                            if (grid[X + Altura * Y] == Num4)
                            {
                                grid[X + Altura * Y] = Ascii37;

                                Console.Write("4");




                            }

                            if (grid[X + Altura * Y] == Num5)
                            {
                                grid[X + Altura * Y] = Ascii38;

                                Console.Write("5");




                            }

                            if (grid[X + Altura * Y] == Num6)
                            {
                                grid[X + Altura * Y] = Ascii39;

                                Console.Write("6");




                            }

                            if (grid[X + Altura * Y] == Num7)
                            {
                                grid[X + Altura * Y] = Ascii40;

                                Console.Write("7");




                            }

                            if (grid[X + Altura * Y] == Num8)
                            {
                                grid[X + Altura * Y] = Ascii41;

                                Console.Write("8");




                            }

                            if (grid[X + Altura * Y] == Num9)
                            {
                                grid[X + Altura * Y] = Ascii42;

                                Console.Write("9");




                            }

                            if (grid[X + Altura * Y] == NumMina1)
                            {

                                Jugar = false;
                                //PERDER
                                Perder();

                            }
                            
                            
                        } //Desvelar

                        if (key == ConsoleKey.V)
                        {

                            if (ContadorFallos <= 4)
                            {

                                if (grid[X + Altura * Y] == Num0 || grid[X + Altura * Y] == Ascii33)
                                {


                                    grid[X + Altura * Y] = NumBandera;
                                    Console.Write("!");
                                    ContadorFallos += 1;
                                }


                                if (grid[X + Altura * Y] == Num1 ||grid[X + Altura * Y] == Ascii34)
                                {

                                    grid[X + Altura * Y] = NumBandera;
                                    Console.Write("!");
                                    ContadorFallos += 1;


                                }

                                if (grid[X + Altura * Y] == Num2 || grid[X + Altura * Y] == Ascii35)
                                {

                                    grid[X + Altura * Y] = NumBandera;
                                    Console.Write("!");
                                    ContadorFallos += 1;


                                }

                                if (grid[X + Altura * Y] == Num3 || grid[X + Altura * Y] == Ascii36)
                                {

                                    grid[X + Altura * Y] = NumBandera;
                                    Console.Write("!");
                                    ContadorFallos += 1;



                                }

                                if (grid[X + Altura * Y] == Num4 || grid[X + Altura * Y] == Ascii37)
                                {


                                    grid[X + Altura * Y] = NumBandera;
                                    Console.Write("!");
                                    ContadorFallos += 1;


                                }

                                if (grid[X + Altura * Y] == Num5 || grid[X + Altura * Y] == Ascii38)
                                {


                                    grid[X + Altura * Y] = NumBandera;
                                    Console.Write("!");
                                    ContadorFallos += 1;


                                }

                                if (grid[X + Altura * Y] == Num6 || grid[X + Altura * Y] == Ascii39)
                                {


                                    grid[X + Altura * Y] = NumBandera;
                                    Console.Write("!");
                                    ContadorFallos += 1;


                                }

                                if (grid[X + Altura * Y] == Num7 || grid[X + Altura * Y] == Ascii40)
                                {


                                    grid[X + Altura * Y] = NumBandera;
                                    Console.Write("!");
                                    ContadorFallos += 1;


                                }

                                if (grid[X + Altura * Y] == Num8 || grid[X + Altura * Y] == Ascii41)
                                {


                                    grid[X + Altura * Y] = NumBandera;
                                    Console.Write("!");
                                    ContadorFallos += 1;


                                }

                                if (grid[X + Altura * Y] == Num9 || grid[X + Altura * Y] == Ascii42)
                                {


                                    grid[X + Altura * Y] = NumBandera;
                                    Console.Write("!");
                                    ContadorFallos += 1;


                                }

                                if (grid[X + Altura * Y] == NumMina1 || grid[X + Ancho * Y] == Ascii43)
                                {

                                    grid[X + Altura * Y] = NumMinaBandera;
                                    Console.Write("@");
                                    ContadorMinas += 1;



                                }








                            }






                        } //Banderas

                        if(key == ConsoleKey.B)
                        {
                            Console.Clear();
                            ELMEGA10 = true;
                            Jugar = false;
                            Instrucciones = true;
                            elegirminas = true;
                            ContadorMinas = 0;
                            ContadorFallos = 0;
                            minas33.Clear();
                            NombreJugador.Clear();


                        } //VOLVER AL MENÚ


                        if (key == ConsoleKey.K)
                        {


                            int Xdel101 = 0;
                            int Ydel101 = 0;
                            int Comodin = 0;

                            Console.SetCursorPosition(Xdel101, Ydel101);

                            for (int El10 = 0; El10 < Altura * Ancho; El10++)
                            {

                                if (grid[El10] == Num0)
                                {

                                    Console.Write("X");

                                }



                                if (grid[El10] >= Num1 && grid[El10] <= Num9)
                                {

                                    Console.Write("X"); // QUE NO SE ESCRIBA NADA DE NADA

                                }


                                if (grid[El10] == NumMina1 && Comodin == 0)
                                {

                                    Comodin++;
                                    Console.Write("M");


                                }
                                else if (grid[El10] == NumMina1)
                                {


                                    Console.Write("X");



                                }


                                if (grid[El10] == Ascii34)
                                {

                                    Console.Write("1");


                                }

                                if (grid[El10] == Ascii35)
                                {


                                    Console.Write("2");




                                }

                                if (grid[El10] == Ascii36)
                                {


                                    Console.Write("3");




                                }

                                if (grid[El10] == Ascii37)
                                {


                                    Console.Write("4");




                                }

                                if (grid[El10] == Ascii38)
                                {


                                    Console.Write("5");




                                }

                                if (grid[El10] == Ascii39)
                                {


                                    Console.Write("6");




                                }

                                if (grid[El10] == Ascii40)
                                {


                                    Console.Write("7");




                                }

                                if (grid[El10] == Ascii41)
                                {


                                    Console.Write("8");




                                }

                                if (grid[El10] == Ascii42)
                                {


                                    Console.Write("9");




                                }

                                if (grid[El10] == NumBandera)
                                {


                                    Console.Write("!");




                                }
                                if (grid[El10] == NumMinaBandera)
                                {


                                    Console.Write("@");




                                }


                                if (El10 % Ancho == 19)
                                {

                                    Console.Write("\n");
                                }

                                if (El10 == 20)
                                {

                                    Ydel101++;

                                }




                            }



                        } //PRUEBA OBJETIVA


                        if (ContadorMinas > 2)
                        {


                            Jugar = false;
                            //GANAR
                            Ganar();

                        } //Condición victoria
                        
                        if (ContadorFallos > 2)
                        {

                            Jugar = false;
                            //PERDER
                            Perder();
                            Jugar = false;


                        } //Condición derrota


                    }

                    
                }


            } //Movimiento y acciones del jugador

            public void Perder()
            {

                
                Console.Clear();
                
                Console.Write("\n\n\n\t\t\t\t HAS PERDIDO " + NombreJugador[0]);
                Console.Write("\n\n\n\t\t\t\t {{{(>_<)}}}");
                Console.Write("\n\n\n\t\t\tPulsa cualquier tecla para volver al menú");
                ConsoleKey key1 = Console.ReadKey(true).Key;
                if (key1 == ConsoleKey.Enter) //Está puesto 'Enter' pero solamente para que después de tocar cualquier tecla se active
                {




                }

                Console.Clear();
                ELMEGA10 = true;
                X = (Ancho / 2);
                Y = (Altura / 2);
                minas33.Clear();
                NombreJugador.Clear();
                Instrucciones = true;
                elegirminas = true;
                ContadorMinas = 0;
                ContadorFallos = 0;
                Jugar = false;
                

            } //Función por si pierde

            public void Ganar()
            {


                Console.Clear();
                
                Console.Write("\n\n\n\t\t\t\t HAS GANADO " + NombreJugador[0]);
                Console.Write("\n\n\n\t\t\t\t (>‘o’)>");
                Console.Write("\n\n\n\t\t\tPulsa cualquier tecla para volver al menú");
                ConsoleKey key1 = Console.ReadKey(true).Key;
                if (key1 == ConsoleKey.Enter) //Está puesto 'Enter' pero solamente para que después de tocar cualquier tecla se active
                {




                }

                Console.Clear();
                ELMEGA10 = true;
                X = (Ancho / 2);
                Y = (Altura / 2);
                minas33.Clear();
                NombreJugador.Clear();
                Instrucciones = true;
                elegirminas = true;
                ContadorMinas = 0;
                ContadorFallos = 0;


            } //Función por si gana

        }
        
                
        static void Main(string[] args)
        {

            Tablero un_tablero = new Tablero();

            un_tablero.Menu();


        }
    }
}





