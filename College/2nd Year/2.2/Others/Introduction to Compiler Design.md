##### OVERVIEW OF LANGUAGE PROCESSING SYSTEM
![500](https://media.geeksforgeeks.org/wp-content/uploads/20210220195102/cd12.png)
#### I. - The structure of a compiler

*a. Analysis (Machine Independent/Language Dependent)* 
*b. Synthesis(Machine Dependent/Language independent)*
         
![600](https://media.geeksforgeeks.org/wp-content/uploads/compilerDesign.jpg)

   A. Lexical Analysis (Scanning)
      1. Definition: Reads characters from the source code to produce tokens.
      2. Process:
         a. Tokenization: Groups characters into meaningful tokens.
         b. Regular Expressions: Defines token patterns.
   
   B. Syntax Analysis (Parsing)
      1. Definition: Analyzes the sequence of tokens to determine if they form valid statements.
      2. Techniques:
         a. Top-Down Parsing: Begins with the start symbol and tries to derive the input string.
         b. Bottom-Up Parsing: Starts with the input string and tries to derive the start symbol.

   C. Semantic Analysis
      1. Definition: Ensures that statements have meaning and checks for semantic errors.
      2. Tasks:
         a. Type Checking: Verifies compatibility of operands and operators.
         b. Scope Resolution: Determines the scope of variables and resolves conflicts.

   D. Code Generation
      1. Definition: Translates intermediate code into target machine code.
      2. Tasks:
         a. Instruction Selection: Chooses appropriate machine instructions.
         b. Register Allocation: Assigns variables to hardware registers.
         c. Code Optimization: Improves efficiency without changing program behavior.

#### II. Lexical Analysis

   **A. - The Role of the Lexical Analyzer**
      1. Definition: The lexical analyzer (scanner) is the initial phase of a compiler that reads the source code and converts it into tokens.
      2. Function:
         a. Tokenization: Divides the source code into meaningful units (tokens) like identifiers, keywords, operators, literals, and symbols.
         b. Error Handling: Detects and reports lexical errors, such as illegal characters or invalid token sequences.

   **B. Input Buffering**
      1. Definition: Input buffering optimizes character reading from the source code.
      2. Techniques:
         a. Double Buffering: Uses a pair of buffers to reduce overhead in accessing input characters.
         b. Lookahead: Allows the lexical analyzer to peek ahead in the input stream for efficient token recognition.

   **C. Recognition of Tokens**
      1. Process:
         a. Lexemes: Sequence of characters matching token patterns defined by regular expressions.
         b. Finite Automata: Models token recognition using state transitions based on input characters.
      2. Techniques:
         a. Regular Expressions: Define patterns for tokens, aiding in token recognition.
         b. Transition Diagrams: Visualize state transitions for token identification.

   **D. The Lexical- Analyzer Generator Lex**
      1. Overview:
         a. Purpose: Automates the generation of lexical analyzers.
         b. Components:
            i. Specifications: Define token patterns using regular expressions.
            ii. Rules: Describe actions for token recognition and error handling.
            iii. Auxiliary Procedures: Support functions for complex token handling.
      2. Output:
         a. Generated Code: Lex translates specifications into efficient C code for the lexical analyzer.
#### III. Syntax Analysis

   **A. Introduction**
      1. Definition: Syntax analysis, or parsing, verifies whether a sequence of tokens conforms to the syntax rules of a formal language.
      2. Purpose: Translates the token stream into a parse tree or syntax tree that represents the syntactic structure of the program.

   **B. Context-Free Grammars (CFG)**
      1. Definition: CFGs specify the syntax rules of programming languages using production rules.
      2. Components:
         a. Terminals: Tokens or symbols that cannot be further decomposed.
         b. Nonterminals: Symbols representing syntactic categories or constructs.
		 c. **Writing a Grammar:**
			 a. Production Rules: Specify how nonterminals can be expanded into sequences of terminals and nonterminals.
			 b. Example: 
				```
				Stmt -> if ( Expr ) Stmt
					  | if ( Expr ) Stmt else Stmt
					  | other_stmt
			```
   **C. Top-Down Parsing**
      1. Recursive Descent Parsing:
         a. Method: Uses recursive procedures corresponding to grammar rules to parse the input.
         b. Predictive Parsing: Enhances efficiency by using lookahead to choose the correct production without backtracking

   **D. Bottom-Up Parsing**
      1. Shift-Reduce Parsing:
         a. Approach: Builds parse trees from the leaves up by reducing a sequence of input tokens.
         b. LR Parsing: Utilizes a state machine to handle deterministic and non-deterministic grammars efficiently.
      **2. LR Parsing Types:**
         a. Simple LR (SLR): Basic form of LR parsing with limited parsing capabilities.
         b. More Powerful LR Parsers:
            i. Canonical LR (CLR): Handles a broader class of grammars by using a more extensive state machine.
            ii. Lookahead LR (LALR): Optimized version of LR parsing that reduces the size of the parsing tables while maintaining parsing power.