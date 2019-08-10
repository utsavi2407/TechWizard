import java.awt.image.BufferedImage;
import java.io.IOException;
import java.net.URL;
import javax.imageio.ImageIO;
import javax.swing.*;
import java.util.Random;
import javax.swing.*;
import java.awt.event.*;
import java.sql.*;
import java.awt.*;

class LoginPage extends Thread implements Runnable{
	
	//panel
	JPanel panel=new JPanel();
	JPanel t_panel=new JPanel();
	JPanel n_panel=new JPanel();
	JPanel s_panel=new JPanel();
	JPanel sub_panel=new JPanel();
	
	
	
	//frames
	JFrame f_login = new JFrame("Login Page");
	JFrame f_start = new JFrame("Start Page");
	public JFrame f_mcq = new JFrame("MCQ Test");
	public JFrame f_final = new JFrame("Final Score");
	public JLabel l_head;
	public JLabel img;
	public JLabel l_timer;
	JTextField t_name;
	JTextField t_phone;
	public int i=1;
	public int j=1;	
	int minutes=15,seconds=0;
	boolean strt = true;
	public int flag=2;
	
	public static int count=0;

	//for MCQ frame
	JTextArea t_qs;
	JLabel l_qs;
	JButton b_next;
	JButton b_submit;
	JButton b_login;
	public JLabel score;
	ButtonGroup bt = new ButtonGroup();
	JRadioButton r_a;
	JRadioButton r_b;
	JRadioButton r_c;
	JRadioButton r_d;
	
	
	// Question Array
	String []question =new String[]{"",
		// Q1
" Q. What is the output of code given below? \n#include <stdio.h>\nint main()\n{ printf(\"%d \", 1);\ngoto l1;\nprintf(\"%d \", 2);  }\nvoid foo() {\nl1 : printf(\"3 \", 3); }",
    
// Q2
"Q. What is the output of code given below?\n#include <stdio.h>\nint main(){ \nint i = 0, j = 0;\nwhile (l1: i < 2)\n{\ni++;\nwhile (j < 3)  {\nprintf(\"loop\n\");\ngoto l1; }  }  }",

// Q3
"Q. Property which allows to produce different executable for different platforms \nin C is called?",

//Q4
"Q. C preprocessors can have compiler specific features.",

//Q5
"Q. What is the output of this C code?\n#include <stdio.h>\n#define foo(m, n) m * n = 10\nint main() {\nprintf(\"in main\n\");  }",

// Q6
"Q. #include <somefile.h> are _______ files and #include “somefile.h” ________ \nfiles.",

// Q7
"Q. #include statement must be written",

// Q8
"Q. Which of the following sorting algorithms can be used to sort a random linked list with minimum time complexity?",

//Q9
"Q. What is the output of this C code?\n#include <stdio.h>\nint main() {\nint one = 1, two = 2;\n#ifdef next\none = 2;\ntwo = 1;\n#endif\nprintf(\"%d, %d\", one, two); }",

// Q10
"Q. What is the output of this C code?\n#include <stdio.h>\nint main()  {\nunsigned int a = 10;\na = ~a;\nprintf(\"%d\n\", a); }",

// Q11
"Q. What is the output of this C code?\n#include <stdio.h>\nint main()  {\nif (7 & 8)\nprintf(\"Honesty\");\nif ((~7 & 0x000f) == 8)\nprintf(\"is the best policy\n\"); }",

// Q12
"Q. What is the output of this C code?\n#include <stdio.h>\nvoid main()  {\nint x = 4;\nint *p = &x;\nint *k = p++;\nint r = p - k;\nprintf(\"%d\", r);  }",

// Q13
"Q. What is the output of this C code?\n#include <stdio.h>\nint main()  {\nvoid foo();\nvoid f()\n{ foo();\n}\nf();\n}\nvoid foo()\n{\nprintf(\"2 \");}",

// Q14
"Q. What is the default return type if it is not specified in function definition?",

// Q15
"Q. What is the output of this C code if there is no error in stream fp?\n#include <stdio.h>\nint main()\n{ FILE *fp;\nfp = fopen(\"newfile\", \"w\");\nprintf(\"%d\n\", ferror(fp));\nreturn 0; }",

// Q16
"Q. stderr is similar to?",

// Q17
"Q. Which of the following function can be used to terminate the main function \nfrom another function safely?",

// Q18
"Q. log(x) function defined in math.h header file is :",

// Q19
"Q. In linux, apart from including math header file, the program is successfully\n executed by which of the following?",

// Q20
"Q. Correct syntax to pass a Function Pointer as an argument",

// Q21
"Q. The sizeof(void) in a 32-bit C is_____",

// Q22
"Q. When is std::bad_alloc exception thrown?",

// Q23
"Q. Which of the following keyword supports dynamic method resolution?",

// Q24
"Q. Which of the following correctly describes C++ language?",

// Q25
"Q. What’s wrong? while( (i < 10) && (i > 24))",

// Q26
"Q. A continue statement causes execution to skip to",

// Q27
"Q. Which of the following is used as a primary storage device ",

// Q28
"Q. Which of the following is not a standard exception built in C++.",

// Q29
"Q. Which of the following relationship is known as inheritance relationship?",

// Q30
"Q. If class A is friend of class B and if class B is friend of class C, which of\n the following is true?",

// Q31
"Q. Originally C was developed as:",

// Q32
"Q. Latency time is:",

// Q33
"Q. What happens when a pointer is deleted twice?",

// Q34
"Q. Which of the following library function below by default aborts \nthe program?",

// Q35
"Q. What defines a general set of operations that will be applied to various\ntypes of data?",

// Q36
"Q. Under which of the following circumstances, synchronization takes place?",

// Q37
"Q. The default value of a static integer variable of a class in Java is",

// Q38
"Q. Which of the following members do get inherited but become private\nmembers in child class",

// Q39
"Q. Which of the following operator cannot be overloaded?",

// Q40
"Q. Which of the following is not a standard exception built in C++.",

// Q41
"Q. Minimum number of temporary variable needed to swap the contents \nof 2 variables is:",

// Q42
"Q. Which data structure can be used to test a palindrome?",

// Q43
"Q. The integer word is defined as",

// Q44
"Q. A decimal digit can be represented by",

// Q45
"Q. Which one of the following is not a valid reserved keyword in C++",

// Q46
"Q.  Each pass through a loop is called a/an",

// Q47
"Q. *ptr++ is equivalenet to:",

// Q48
"Q. Which of the following language is not supported by C++?",

// Q49
"Q. Expression C=i++ causes",

// Q50
"Q. If a member needs to have unique value for all the objects of that same \nclass, declare the member as",

// Q51
"Q. When class B is inherited from class A, what is the order in which the \nconstructers of those classes are called",

// Q52
"Q. Which of the following is the most general exception handler that catches\nexception of ‘any type’?",

// Q53
"Q. Inline functions are invoked at the time of",

// Q54
"Q. What is the implicit pointer that is passed as the first argument for \nnonstatic member functions?",

// Q55
"Q.functions can return enumeration constants in c?",

// Q56
"Q. Within main, return expr statement is equivalent to.",

// Q57
"Q. What happens when we use\nfprintf(stderr, “error: could not open filen”);",

// Q58
"Q. function fabs defined math.h header file takes argument of type integer.",

// Q59
"Q. What type of inputs are accepted by mathematical functions?",

// Q60
"Q. Which of the following is not a valid mathematical function?",

// Q61
"Q. How to call a function without using the function name to send \nparameters?",

// Q62
"Q. Which of the following is not possible in C?",

// Q63
"Q. What is the sizeof(char) in a 32-bit C compiler?",

// Q64
"Q. Which of the following is not an operator in C?",

// Q65
"Q. Which among the following has the highest precedence?",

// Q66
"Q. What type of value does sizeof return?",

// Q67
"Q. Binary trees can have how many children?",

// Q68
"Q. Which keys allows user to enter frequently used operations in a single\n key stroke?",

// Q69
"Q. _________ is used for detecting mouse motion.",

// Q70
"Q. The maximum length of the string in a bit string of contiguous bits is",

// Q71
"Q. Trackball is",

// Q72
"Q. A 16-bit displacement that references a memory location using any of the \naddressing modes is",

// Q73
"Q. Identify the language :\nprintf(\"Hello, World! \");",

// Q74
"Q. Identify the language :\nint main() {\ncout << \"Hello World\";\nreturn 0; }",

// Q75
"Q. Identify the language :\npublic class Hello {\npublic static void main(String []args) {\nSystem.out.println(\"Hello World\"); } }",

// Q76
"Q. Identify the language :\n>>> print \"Hello, World!\"",

// Q77
"Q. Identify the language :\nPrelude> \"Hello\"\n\"Hello\"\nPrelude> 3 * 5\n15",

 // Q78
 "Q. Identify the language :\nFunction Func_Name(params...) : Return_Value;\nProcedure Proc_Name(params...);",

// Q79
"Q. Identify the language :\nalert(\"HELLO! I AM ALERT BOX!!!\");",

// Q80
"Q. Identify the language :\n<?\nprint \"An example with single line comments\";\n?>",

 // 81
"Q. Frames from one LAN can be transmitted to another LAN via the device : ",

// 82
"Q. Which of the following type of class allows only one object of it to be created?",

// 83
"Q. Which of the following statements is correct?",

// 84
"Q. Which of the following concepts of OOPS means exposing only necessary information to client?",

// 85
"Q. Why reference is not same as a pointer?",

// 86
"Q. cout is a/an __________ ",

// 87
"Q. How many types of polymorphisms are supported by C++?",

// 88
"Q. Which of the following is an abstract data type?",

// 89
"Q. Which of the following correctly describes overloading of functions?",

// Q 90
"Q. How Late binding is implemented in C++?",

// Q 91
"Q. Which of the following cannot be used with the keyword virtual?",

// Q 92
"Q. Which of the following problem causes an exception?",

// Q 93
"Q. Which of the following is the correct way of declaring a function as constant?",

// Q 94
"Q. In which of the following a virtual call is resolved at the time of compilation?",

// Q 95
"Q. Which of the following is used to make an abstract class?",

// Q 96
"Q. What is correct about the static data member of a class?",

// Q 97
"Q. A static data member is given a value",

// Q 98
"Q. What will be the result of the expression 13 & 25?",

// Q 99
"Q. Which of the statements are true ?\nI. Function overloading is done at compile time.\nII. Protected members are accessible to the member of derived class.\nIII. A derived class inherits constructors and destructors.\nIV. A friend function can be called like a normal function.\nV. Nested class is a derived class.",

// Q 100
"Q.  At which point of time a variable comes into existence in memory is \ndetermined by its",

// Q 101
"Q. Which of the following operator can be overloaded through \nfriend function?",

// Q 102
"Q. Function templates can accept : " 
};
		//System.out.println(question[i]);
		
		
	
	String options[][] = new String[][]
	{
	{""},
	{"A) 1 2 3", "B) 1 3","C) 1 3 2 ","D) Compilation error"},//1
	{"A) loop loop","B) Compilation error","C) loop loop loop loop","D) Infinite loop"},//2
	{"A) File inclusion","B) Selective inclusion","C) Conditional compilation","D) Recursive macros"},//3
	{"A) true","B) false","C) Depends on the standard","D) Depends on the platform"},//4
	{"A) In main","B) Compilation error as lvalue is required for the expression m*n=10","C) Preprocessor error as lvalue is required for the expression m*n=10","D) None of the mentioned"},//5****
	{"A) Library, Library","B) Library, user-created header","C) User-created header, library","D) They can include all types of file"},//6
	{"A) Before main()","B) Before any scanf/printf","C) After main()","D) It can be written anywhere"},//7
	{"A) Insertion Sort","B)Quick Sort", "C)Heap Sort","D) Merge Sort"},//8
	{"A) 1, 1","B) 1, 2","C) 2, 1","D) 2, 2"},//9
	{"A) -9","B) -10","C) -11","D) 10"},//10
	{"A) Honesty is the best policy","B) Honesty","C) is the best policy","D) No output"},//11
	{"A) 4","B) 8","C) 1","D) Run time error"},//12
	{"A) 2 2","B) 2","C) Compile time error","D) Depends on the compiler"},//13
	{"A) void","B) int","C) double","D) short int"},//14
	{"A) Compilation error","B) 0","C) 1","D) Any nonzero value"},//15
	{"A) stdin","B) stdout","C) Both stdout and stdin","D) None of the mentioned"},//16
	{"A) return(expr);","B) exit(expr);","C) abort();","D) Both exit(expr); and abort();"},//17
	{"A) Natural base logarithm","B) Logarithm to the base 2","C) Logarithm to the base 10","D) None of the mentioned"},//18
	{"A) cc filename.c","B) cc filename.c -lc","C) cc -math filename.c","D) cc -lm filename.c"},//19
	{"A) void pass(int (*fptr)(int, float, char)){}","B) void pass(*fptr(int, float, char)){}","C) void pass(int (*fptr)){}","D) void pass(*fptr){}"},//20
	{"A) 0","B) 1","C) 2","D) 4"},//21
	{"A) When new operator cannot allocate memory","B) When alloc function fails","C) When type requested for new operation is  bad,thisexception is thrown","D) When delete operator cannot delete the allocated (corrupted) object"},//22*****
	{"A) abstract","B) Virtual","C) Dynamic","D) Typeid"},//23
	{"A) Statically typed language","B) Dynamically typed language","C) Both Statically and dynamically typed language","D) Type-less language"},//24
	{"A) the logical operator && cannot be used in a test condition","B) the while loop is an exit-condition loop","C) the test condition is always false","D) the test condition is always true"},//25
	{"A) the return 0; statement","B) the first statement after the loop","C) the statement following the continue statement","D) the next iteration of the loop"},//26
	{"A) Magnetic tape","B) PROM", " C) Floppy disk ","D) None of the above"},//27
	{"A) std::bad_creat","B) std::bad_alloc","C) std::bad_cast","D) std::bad_typeid"},//28
	{"A) 'has-a’ relationship","B) ‘is-a’ relationship","C) association relationship","D) none of the above"},//29
	{"A) Class C is friend of class A","B) Class A is friend of class C","C) Class A and Class C do not have any friend relationship","D) None of the above"},//30
	{"A) System programming language","B) General purpose language","C) Data processing language","D) None of above"},//31
	{"A) Time taken by read/write head mechanism to position itself over appropriate cylinder","B) Time taken to transfer a dta from memory","C) Time taken by appropriate sector to come under read/write head","D) None of above"},//32****
	{"A) It can abort the program","B) It can cause a failure","C) It can cause an error","D) It can cause a trap"},//33
	{"A) Terminate()","B) end()","C) Abort()","D) exit()"},//34
	{"A) Template class","B) Function template","C) Class template","D) Both a and c above"},//35
	{"A) When the file is closed","B) When the buffer is empty","C) Explicitly, with manipulators","D) both a and c"},//36
	{"A) 0 ","B) 1", "C) Garbage value ","D) Null","E) -1"},//37
	{"A) Public","B) Private","C) Protected","D) All the above"},//38
	{"A) == (equality operator)","B) –> (row operator)","C) :: (cope resolution operator)","D) Both a and c"},//39
	{"A) std::bad_creat","B) std::bad_alloc","C) std::bad_cast","D) std::bad_typeid"},//40
	{"A) 1","B) 2","C) 3","D) 0"},//41
	{"A) Tree","B Heap","C) Stack","D) Priority queue"},//42
	{"A) signed 8-bit data","B) unsigned 16-bit data","C) signed 16-bit data","D) signed 32-bit data"},//43
	{"A) unsigned integer","B) signed integer","C) unpacked BCD","D) packed BCD"},//44
	{"A) Explicit","B) Public","C) Implicit","D) Private"},//45
	{"A) enumeration","B) iteration","C) culmination","D) pass through"},//46
	{"A) ptr++","B) *ptr","C) ++*ptr","D) None of the above"},//47
	{"A) Exception Handling","B) Reflection","C) Operator Overloading","D) Namespaces"},//48
	{"A) Value of i assigned to C and then i incremented by 1","B) i to be incremented by 1 and then value of i assigned to C","C) Value of i assigned to C","D) i to be incremented by 1"},//49
	{"A) Global variable outside class","B) Local variable inside constructor","C) Static variable inside class","D) Dynamic variable inside class"},//50
	{"A) Class A first Class B next","B) Class B first Class A next","C) Class B’s only as it is the child class","D) Class A’s only as it is the parent class"},//51
	{"A) catch(std::exception)","B) catch(std::any_exception)","C) catch(...)","D) catch()"},//52
	{"A) Run time","B) Compile time","C) Depends on how it is invoked","D) Both b and c"},//53
	{"A) ‘self’ pointer","B) std::auto_ptr pointer","C) ‘Myself’ pointer","D) ‘this’ pointer"},//54
	{"A) true","b) false","C) depends on the compiler","D) depends on the standard"},//55
	{"A) abort(expr)","B) exit(expr)","C) ferror(expr)","D) none of the mentioned"},//56
	{"A) The diagnostic output is directly displayed in the output.","B) The diagnostic output is pipelined to the output file.","C) The line which caused error is compiled again.","D) The program is immediately aborted."},//57
	{"A) True","B) False","C) Depends on the implementation","D) Depends on the standard"},//58
	{"A) short","B) int","C) float","D) double"},//59
	{"A) frexp(x);","B) atan2(x,y);","C) srand(x);","D) fmod(x);"},//60
	{"A) typedefs","B) Function pointer","C) Both typedefs and Function pointer","D) None of the mentioned"},//61
	{"A) Array of function pointer","B) Returning a function pointer","C) Comparison of function pointer","D) None of the mentioned"},//62
	{"A) 1 bit","B) 2 bits","C) 1 Byte","D) 2 Bytes"},//63
	{"A) ,","B) sizeof()","C) ~","D) None of the mentioned"},//64
	{"A) &","B) <<","C) sizeof()","D) &&"},//65
	{"A) char","B) short","C) unsigned int","D) long"},//66
	{"A) 2","B) any number of children","C) 0 or 1 or 2","D) 0 or 1"},//67
	{"A) Function keys","B) Cursor control keys","C) Trackball","D) Control keys"},//68
	{"A) Optical sensor","B) Rollers on the bottom of mouse","C) Both a and b","D) Sensor"},//69
	{"A) 2 MB","B) 4 MB","C) 2 GB","D) 4 GB"},//70
	{"A) Two-dimensional positioning device","B) Three- dimensional positioning device","C) Pointing device","D) None of the mentioned"},//71
	{"A) Pointer","B) Character","C) BCD","D) Offset"},//72
	{"A) B","B) C","C) C++","D) Fortran"},//73
	{"A) Java","B) C","C) C++","D) Fortran"},//74
	{"A) Java","B) C","C) C++","D) Fortran"},//75
	{"A) B","B) C","C) Python","D) Fortran"},//76
	{"A) Pascal","B) C","C) Haskell","D) Fortran"},//77
	{"A)Lisp","B) C","C) Pascal","D) Fortran"},//78
	{"A) Python","B) JavaScript","C) C++","D) Fortran"},//79
	{"A) JavaScript","B) Ajax"," C) PHP","D) Fortran"},//80
	
	{"A)Router","B)Bridge","C)Repeater","D)Modem"},
	{"A)Virtual class","B)Abstract class","C)Singleton class","D)Friend class"},
	{"A)Base class pointer cannot point to derived class.","B)Derived class pointer cannot point to base class.","C)Pointer to 		derived class cannot be created.","D)Pointer to base class cannot be created."},
	{"A)Encapsulation","B)Abstraction","C)Data hiding","D)Data binding"},
	{"A)A reference can never be null.","B)A reference once established cannot be changed.","C)Reference doesn't need an explicit 		dereferencing mechanism.","D)All of the above."},
	{"A)operator","B)function","C)object","D)macro"},
	{"A)1","B)2","C)3","D)4"},
	{"A)int","B)double","C)string","D)Class"},
	{"A)Virtual polymorphism","B)Transient polymorphism","C)Ad-hoc polymorphism","D)Pseudo polymorphism"},
	{"A)Using C++ tables","B)Using Virtual tables","C)Using Indexed virtual tables","D)Using polymorphic tables"},
	{"A)class","B)member functions","C)constructor","D)destructor"},
	{"A)Missing semicolon in statement in main().","B)A problem in calling function.","C)A syntax error.","D)A run-time error."},
	{"A)const int ShowData(void) { /* statements */ }","B)int const ShowData(void) { /* statements */ }","C)int ShowData(void) const 	{ /* statements */ }","D)Both A and B"},
	{"A)From inside the destructor.","B)From inside the constructor.","C)From inside the main().","D)Both A and B."},
	{"A)Declaring it abstract using static keyword.","B)Declaring it abstract using virtual keyword.","C)Making at least one member 	function 	as virtual function.","D)Making at least one member function as pure virtual function."},
	{"A)A static member function can access only static data members of a class.","B)A static data member is shared among all the 		object of the class.","C)A static data member can be accessed directly from main().","D)Both A and B."},
	{"A)Within the class definition.","B)Outside the class definition.","C)When the program is exeuted","D)Never."},
	{"A)38","B)25","C)9","D)12"},
	{"A)I, II, III","B)II, III, V","C)III, IV, V","D)I, II, IV"},
	{"A)Scope","B)Storage class","C)Data type","D)All of the above."},
	{"A)->","B)=","C)( )","D)*"},
	{"A)Any type of parameters","B)Only one parameter","C)Only parameters of the basic type","D)Only parameters of the derived 		type."}
	};
	
	String answer[] = new String[]{"","",
	//1.
	 "d",

	//2.
	 "b",

	//3. 
	"c",

	//4. 
	"a",

	//5. 
	"a",

	//6.
	 "d",

	//7.
	 "b",

	//8. 
	"d",

	//9.
	 "b",

	//10.
	 "c",

	//11.
	 "c",

	//12.
	 "c",

	//13.
	 "d",

	//14.
	 "b",

	//15.
	 "b",

	//16. 
	"a",

	//17.
	  "b",

	//18.
	  "a",

	//19. 
	"d",

	//20.
	 "a",

	//21. 
	 "b",

	//22. 
	 "d",

	//23. 
	 "b",

	//24.
	 "a",

	//25.
	 "c",

	//26.
	 "d",

	//27.
	 "a",

	//28.
	  "b",

	//29.
	 "b",

	//30.
	  "c",

	//31.
	  "a",

	//32.
	 "c",

	//33.
	  "d",

	//34.
	 "a",

	//35. 
	 "d",

	//36.
	 "b",

	//37.
	  "a",

	//38.
	 "d",

	//39. 
	 "d",

	//40.
	 "a",

	//41. 
	 "d",

	//42. 
	"c",

	//43.
	  "c",

	//44.
	  "c",

	//45. 
	 "c",

	//46. 
	 "b",

	//47. 
	"d",

	//48. 
	 "b",

	//49. 
	 "a",

	//50.
	 "b",

	//51.
	 "a",

	//52. 
	 "c",

	//53. 
	 "b",

	//54. 
	 "d",

	//55. 
	"a",

	//56. 
	 "b",

	//57. 
	 "a",

	//58. 
	 "b",

	//59. 
	 "d",

	//60. 
	"d",

	//61. 
	 "b",

	//62. 
	"d",

	//63. 
	 "c",

	//64. 
	 "d",

	//65. 
	 "c",

	//66. 
	 "c",

	//67. 
	 "c",

	//68.
	 "a",

	//69.
	 "c",

	//70.
	  "d",

	//71.
	  "a",

	//72. 
	 "d",

	//73. 
	 "b",

	//74. 
	"b",

	//75.
	 "b",

	//76.
	 "b",

	//77. 
	"b",
	 
	//78. 
	"b",

	//79. 
	"b",

	//80. 
	"b",
	
 	
	//1.
	 "b",
 	
	//2.
	 "a",
	 	
	//3.
	"b",
	 	
	//4.
	"c",
	  	
	//5.
	"d",
	  	
	//6.
	"c",
	  	
	//7
	"b",
	  	
	//8.
	"d",
 	
	//9
	 "c",
	
	//10
	 "b",
	
	//11
	 "c",
	
	//12
	 "d",
	
	//13.
	 "c",
	
	//14
	 "d",
	
	//15
	 "d",
	
	//16
	 "d",
	
	//17
	 "d",
		
	//18	
	 "c",
	
	//19	
	  "d",
	
	//20
	  "b",	
	
	//21
	 "d",
	      
	//22      
	  "c" };
	
	
	public String selected="";
	public String ans="";
	String Username;
	String Number;
	

	public void login(){
	
		Font f = new Font(Font.SANS_SERIF,Font.BOLD, 35);
		
		// frame objects
		JLabel l_name = new JLabel("NAME");
		JLabel l_phone = new JLabel("PHONE NUMBER");
		JLabel l_head = new JLabel("WELCOME TO TECH WIZARD");		
		t_name = new JTextField();
		t_phone = new JTextField();
		JButton b_login = new JButton("LOGIN");


		
		//background image
		img=new JLabel(new ImageIcon("//home/shree/Desktop/bgg.jpg"));
		img.setSize(200,200);
		img.setBounds(0,0,1366,768);
		f_login.add(img);
		img.setLayout(new FlowLayout());
		f_login.setContentPane(img);
	    
	   	// String name;
	   	 int phone;
	   	 	
	   	//Setting Fonts
	   	l_name.setFont(new Font("SansSerif Plain",Font.PLAIN,20));
	   	l_phone.setFont(new Font("SansSerif Plain", Font.PLAIN, 20));
	   	l_head.setFont(new Font("Serif", Font.BOLD, 34));
	   	//l_qs.setLayout(new FlowLayout(FlowLayout.CENTER, 10, 10));
	   	Color cc = new Color(255,1,1);


		panel.setFont(new Font("Serif", Font.BOLD, 50));		
		

	   	/*l_name.setForeground(Color.white);
	   	l_phone.setForeground(Color.white);
	   	l_head.setForeground(Color.white);*/
	   	
	   	
	   	
	   	l_name.setForeground(cc);
	   	l_phone.setForeground(cc);
	   	l_head.setForeground(cc);
	   	
	   	//l_timer.setForeground(cc);
		
		// setting bounds
		l_name.setBounds(400,250,100,50);
		l_phone.setBounds(400,350,200,50);
		l_head.setBounds(350,60,700,100);
		t_name.setBounds(675,260,200,30);
		t_phone.setBounds(675,360,200,30);
		b_login.setBounds(600,500,100,30);
		/*}catch(IOException e) {
			e.printStackTrace();
			}*/
		
		// onclick submit button
		b_login.addActionListener(new ActionListener(){  
			public void actionPerformed(ActionEvent e){  
            	
            	String name = t_name.getText();
            	String phone = t_phone.getText();
            	
            	if(connect(name,phone)){
            		JOptionPane.showMessageDialog(f_login,"You have successfully logged in");
            		 StartPage();
            		}
            	else
            		JOptionPane.showMessageDialog(f_login,"Invalid Login! Try Again");
        }  
    });  
		
		// adding object to frame
		f_login.add(l_name);
		f_login.add(l_phone);
		f_login.add(l_head);		
		f_login.add(t_name);
		f_login.add(t_phone);
		f_login.add(b_login);
		f_login.setSize(1360,768);  
    		f_login.setLayout(null);  
	   	f_login.setVisible(true);
	}

	public boolean connect(String Name,String Phone){
		//jdbc objects
		Connection con;
    		Statement st;
	   	ResultSet rs;
	    
		try{  
			Class.forName("com.mysql.jdbc.Driver");  
			con=DriverManager.getConnection("jdbc:mysql://localhost/techw","root","root");   
			st=con.createStatement();  
			rs=st.executeQuery("select * from techm where phone='"+Phone+"'");
		
			while(rs.next())  {
			
			 	Username = rs.getString("name");
			 	Number = rs.getString("phone");
			 	
			 	if(Name.equals(Username) && Phone.equals(Number)){
			 		return true;
			 	}
			}
			}catch(Exception e){

				 System.out.println(e);
			}  
			return false;  
		}
		
	public void StartPage(){
		
		// Start button
		JButton b_start = new JButton("START QUIZ");
		b_start.setBounds(530,580,150,50);
		
		/* try{
    		URL url = new URL("http://www.wallpapersin4k.org/wp-content/uploads/2017/04/Black-Wallpaper-HD-1366x768-7.jpg");
		Image image = ImageIO.read(url);*/
		
		//background image
		img=new JLabel(new ImageIcon("//home/shree/Desktop/bgg2.jpg"));
		img.setSize(100,100);
		img.setBounds(0,0,1366,768);
		f_start.add(img);
		img.setLayout(new FlowLayout());
		f_start.setContentPane(img);
		
		
		
	    	JTextArea area=new JTextArea("\tINSTRUCTIONS\n\n\n1)The following MCQ Quiz is of 15 minutes.\n\n2)The Quiz consists of 100 questions.\n\n3)Try to solve maximum number of questions.\n\n4)Each question carries 1 mark each.\n\n5)Once you click on 'NEXT' you CANNOT go back\n   to the 'PREVIOUS' question\n\n\n\tALL THE BEST");
	    	area.setFont(new Font("Comic Sans MS", Font.BOLD, 20));
	    	area.setBounds(350,90,850,400);  
        	area.setEditable(false);
        	area.setOpaque(false);
        	area.setForeground(Color.white);
        	f_start.add(area); 
        	area.setRows(5);
        	 
        	//f.setSize(300,300);  
        	f_start.setLayout(null);  
        	f_start.setVisible(true);
        	
		
		// action after start
		b_start.addActionListener(new ActionListener(){  
			public void actionPerformed(ActionEvent e){  
				McqTest();
            	}
            	});
		
		//add objects to frame
		f_login.setVisible(false);
		f_start.setVisible(true);
		f_start.setSize(1360,768);
		f_start.setLayout(null);
		f_start.add(b_start);
		//f_start.add(instruction);
		
	}
	
	
	
	public void McqTest(){
	
		//panel  
      		panel.setBounds(10,0,800,550);
        	f_mcq.setContentPane(panel);
        	panel.setOpaque(false);
        	panel.setLayout(null);
        	
        	//Timer panel
        	t_panel.setBounds(1100,20,160,35);    
        	t_panel.setBackground(Color.black);  
        	f_mcq.setContentPane(t_panel);
        	t_panel.setVisible(true);
        	
        	//score panel
	      	s_panel.setBounds(1000,600,120,50);    
        	s_panel.setBackground(Color.white);  
        	f_mcq.setContentPane(s_panel);
        	s_panel.setVisible(true);

		
		//background image
		img=new JLabel(new ImageIcon("//home/shree/Desktop/bgg6.jpg"));
		img.setSize(100,100);
		img.setBounds(0,0,1366,768);
		f_mcq.add(img);
		img.setLayout(new FlowLayout());
		f_mcq.setContentPane(img);
		
		
		//start timer
		new Thread(this).start();
		
		// frame objects
		t_qs = new JTextArea();
		l_timer = new JLabel("TIME");
		//l_timer.setForeground(Color.white);
		b_next = new JButton("NEXT");
		b_submit = new JButton("SUBMIT");
		
				
		
		
		r_a = new JRadioButton();
		r_b = new JRadioButton();
		r_c = new JRadioButton();
		r_d = new JRadioButton();
		bt.add(r_a);
		bt.add(r_b);

		bt.add(r_c);
		bt.add(r_d);
		
		//setting bounds
		b_next.setBounds(100,600,100,50);
		b_submit.setBounds(1000,600,150,50);
		
		t_qs.setBounds(20,10,800,250);
		t_qs.setWrapStyleWord(true);
		t_qs.setEditable(false);
		t_qs.setColumns(100);
		t_qs.setRows(12);
		l_timer.setBounds(920,55,100,50);	
		r_a.setBounds(10,251,800,50);
		r_b.setBounds(10,301,800,50);
		r_c.setBounds(10,351,800,50);
		r_d.setBounds(10,401,800,50);

		//foreground color
		r_a.setForeground(Color.white);
		r_b.setForeground(Color.white);
		r_c.setForeground(Color.white);
		r_d.setForeground(Color.white);
		t_qs.setForeground(Color.white);
		b_next.setForeground(Color.black);
		b_submit.setForeground(Color.black);
		
		l_timer.setForeground(Color.white);

				
		
		//background color		
		/*r_a.setBackground(Color.black);
		r_b.setBackground(Color.black);
		r_c.setBackground(Color.black);
		r_d.setBackground(Color.black);*/
		
		//Set opaque
		
		r_a.setOpaque(false);
		r_b.setOpaque(false);
		r_c.setOpaque(false);
		r_d.setOpaque(false);
		
		//button fonts
		r_a.setFont(new Font("Trebuchet MS", Font.BOLD, 17));
		r_b.setFont(new Font("Trebuchet MS", Font.BOLD, 17));
		r_c.setFont(new Font("Trebuchet MS", Font.BOLD, 17));
		r_d.setFont(new Font("Trebuchet MS", Font.BOLD, 17));						
		
		//t_qs.setBackground(Color.black);
		t_qs.setOpaque(false);
		b_next.setBackground(Color.white);
		b_submit.setBackground(Color.white);

		l_timer.setBackground(Color.black);


		
		//panel background
		
		//panel.setBackground(Color.white);
		n_panel.setBackground(Color.white);
		//s_panel.setBackground(Color.black);
		t_panel.setBackground(Color.black);
		
		//panel fonts
		t_qs.setFont(new Font("Trebuchet MS", Font.BOLD, 17));
		b_next.setFont(new Font("Trebuchet MS", Font.PLAIN, 20));
		b_submit.setFont(new Font("Trebuchet MS", Font.PLAIN, 20));

		l_timer.setFont(new Font("Trebuchet MS", Font.BOLD, 20));
		
		l_timer.setForeground(Color.white);
		//bt.setSize(100,100);
		
		//get first question
		getQs(1);
		
		//get question on next button
		b_next.addActionListener(new ActionListener(){  
			public void actionPerformed(ActionEvent e){ 
			
					getQs(++i);
					j++;		
					flag++;
					
					
					//bt.setSelected(bt.getSelection(), false);
					
					if(flag<=102){
				        	b_next.setVisible(true);
					}
					else{
				        	b_next.setVisible(false);
					}
					
					//passing the selected value to check the answer
					
					// j is the counter to keep the track of the answer array instead of i
					
					check(selected,j);
		
					
			}
			});
			
			
		b_submit.addActionListener(new ActionListener(){  
			public void actionPerformed(ActionEvent e){ 
								
				final_score();			
			}
			});
				
		
		//add to panel
		panel.add(t_qs);
		panel.add(r_a);
		panel.add(r_b);
		panel.add(r_c);
		panel.add(r_d);
		//panel.add(l_timer);
		
		
		//Timer panel add
		
		t_panel.add(l_timer);		
			
			
		//add objects
		f_mcq.add(b_submit);

		f_mcq.add(b_next);
		f_mcq.add(panel);
		f_mcq.add(t_panel);
		f_mcq.add(n_panel);
		f_mcq.add(s_panel);
		f_mcq.add(sub_panel);	
		
				
		//MCQ frame
		f_mcq.setLayout(null);
		f_start.setVisible(false);
		f_mcq.setVisible(true);
		f_mcq.setSize(1360,768);
	}
	
	public void final_score(){
	
		// final label
		JLabel l_thank = new JLabel("THANK YOU FOR PLAYING!");
		
		
		//Background image
		img=new JLabel(new ImageIcon("//home/shree/Desktop/bgg7.jpg"));
		img.setSize(100,100);
		img.setBounds(0,0,1366,768);
		f_final.add(img);
		img.setLayout(new FlowLayout());
		f_final.setContentPane(img);
		
		//setting object
		score = new JLabel("Final Score : ");
		score.setBounds(500,300,500,200);
		score.setForeground(Color.white);
		score.setFont(new Font("Trebuchet MS", Font.BOLD, 30));
		l_thank.setBounds(450,100,700,200);
		l_thank.setForeground(Color.white);
		l_thank.setFont(new Font("Trebuchet MS", Font.BOLD, 30));
		
		//Displaying final score
		score.setText("Your Final Score : "+count);
		
		
		Connection con;
    		Statement st;
	   	ResultSet rs;
	   	int dummy;
	   	long ph = Integer.parseInt(Number);
	    
		try{  
			Class.forName("com.mysql.jdbc.Driver");  
			con=DriverManager.getConnection("jdbc:mysql://localhost/techw","root","root");   
			st=con.createStatement();  
			dummy=st.executeUpdate("update techm set marks='"+count+"' where phone='"+Number+"'");
		
			}catch(Exception e){

				 System.out.println(e);
			}  
		
		//adding object
		f_final.add(score);
		f_final.add(l_thank);
		
		//Final Frame
		f_final.setLayout(null);
		f_mcq.setVisible(false);
		f_final.setVisible(true);
		f_final.setSize(1360,768);
		/*}catch(IOException e) {
			e.printStackTrace();
			}*/
	    
	}
	
	public void getQs(int i){
	
		t_qs.setText(question[i]);
		r_a.setText(options[i][0]);
		r_b.setText(options[i][1]);
		r_c.setText(options[i][2]);
		r_d.setText(options[i][3]);
		
		
		r_a.addActionListener(new ActionListener(){  
		public void actionPerformed(ActionEvent e){ 
			if(r_a.isSelected()){   
				selected=""; 
				selected = "a";	
				r_a.setSelected(false);
				}		
		
		}});
		

		r_b.addActionListener(new ActionListener(){  
		public void actionPerformed(ActionEvent e){
			if(r_b.isSelected()){   
				selected=""; 
				selected = "b";	
				r_b.setSelected(false);
				
			}		 
		
		}});


		r_c.addActionListener(new ActionListener(){  
		public void actionPerformed(ActionEvent e){ 
			if(r_c.isSelected()){   
				selected=""; 
				selected = "c";	
				r_c.setSelected(false);
				
			}		
				
		}});


		r_d.addActionListener(new ActionListener(){  
		public void actionPerformed(ActionEvent e){ 
			if(r_d.isSelected()){   
				selected=""; 
				selected = "d";	
				r_d.setSelected(false);
					
			}						
		}});

		
		
		
		
			
	}
	
	//To check the selected answer and update the score !!
		
	public void check(String ans,int k){
		//System.out.println(ans);
		//System.out.println(answer[k]);
		if(ans.equals(answer[k])){
			count++;
		}
		//l_score.setText("Score : "+count);
	}
	
	//thread run
	
	public void run() 
	{
		while(strt)
		{
			try 
			{
			   Thread.sleep(1000);
			   seconds--;
				if(seconds < 0)
				{
					seconds = 59;
					minutes--;
				}
				l_timer.setText("Time : "+minutes+" : "+seconds);

				if(minutes==0 && seconds==0)
				{
					strt=false;
					final_score();
				}
			}
		 catch(InterruptedException ex)  { System.out.print(ex); }
		}
	}
	
}



  
class TechMania{	
	public static void main(String args[]){
				
		LoginPage obj1 = new LoginPage();
		obj1.login();
	}
}
