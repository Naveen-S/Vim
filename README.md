# Vim
#### My journey with VIM!! 


   vim : vi Improved.

   vi refers to visual.
    
### VIM modes
    
   *  Normal mode - Where you enter commands. You'll be in normal mode when you open a file.
    
   *  Insert mode - Where you type in the content of the file, need to press i to enter 
                     insert mode after opening a file.
   
   *  Line/command mode - Where you enter command to either save/quit or do some quick operation. 
                  Press `Esc and :` to enter this mode.  
                  
  
  ### Basic commands
  
 #####  Save 

>     wq  
 write and quit 
 
 ##### quit
 
 > q
 quit when there is no changes to the file during that session, if there is it give a error saying `no write since last change`. Which means you havn't saved after last change that was being done. 
 
 > q!
 exclamation acts as a forced option, `q!` forced quit.
 
 
 ### Navigation
 
        j : move down a line
        k : move up a line
        h : move left one character
        l : move right one character
        
   SIDENOTE:
   * Arrow keys works just fine.
   
   
   ##### Move page wise
   
        Ctrl + f : forward one page
        Ctrl + b : backward one page
        
   EXTRA:
   * `z + enter` move the view, keeping your cursor position fixed.
   
   #####  Move by word 
        
        w : move one word forward
        W : move one word forward ignoring the punctuations.
        b : move one word backward
        B : move one word forward ignoring the punctuations.
    
  
  #####  Move using regular expression
    
        ^ or 0 : move to start of the line
        $      : move to end of the line
        
  ##### Move via goto
        
        gg      : start of the file
        G       : end of the file
        
        2gg     : go to second line of the file
        2G      : go to second line of the file
        
        ngg/nG  : go to nth line. (n can be any number )
        
        ctrl + g : Show more info about the file, filename line number etc.
        
  ##### using command mode
        
        :10 - go to 10th line of the file.
        
        :$ - last line of the file.
     
            
 ### Deleting
 
        x   : delete the next letter.
        X   : delete the previous letter.
   
        dw  : delete a word.
   *  pattern is `d` for delete and `w` for move by word. 
                
            d3w  : delete 3 words
       
            3dw  : delete a word and repeat 3 times.
       
   * Generic pattern ( count{operation}count{motion} )
       
        count| operation | count | motion | 
       -------|-----------|-------|-----------
       | 3    |      d    |    3  |   w    |  
        
        delete 3 words and repeat it 3 times.
        
        which is similar to 9dw: delete word 9 times.
    
                  
            dd       : delete an entire line.
            d$ or D  : delete till end of the line.
            
            dG  : delete till end of the file.
            dgg : delete from cursor position to start of the file.
       
       NOTE: `.` is used to repeat the previous command.
                  
                  
 ### Help system
      
     > :help or :h 
     
   to get help for particular command.
   
   ex:
         
       :h dd
   Give information about `dd` command.
   
   
   Note: Whatever use you inside square bracket in vim help system is optional. 
        ex: 
           
           :h dd
            
            dd                  Delete [count] lines [into register x] |linewise|. 
    
   specifying count and into register x is optional.
   
   
    Ctrl + o        : to go previous help search
    Ctrl + i        : to go next help search
    Ctrl + w + w    : toggle between your file and help file.
    
    
### Cut, copy and paste

* Comparison between standard editors vs vim 
   
   Standard | Vim  |
   ---------|-----------
   cut     |   delete d
   copy    |   yank   y
   paste   |   put    p
   
   undo : u
   Redo : ctrl + R

   Same pattern + motion works here as well.
   
         3yy - copy 3 lines.
         
   #### Registers
        
        Registers are storage locations.
        
   Types of registers:
    
        *   Unnamed registers   : ""
        *   Numbered registers  : "0 "1 .... "9
        *   named registers     : "a "b .... "z 

    Notes about Numbered registers:
        
        * "0    : stores the last yanked data.
        * "1    : stores the last deleted data.
        * ""    : stores the data of last operation
        
   
    Notes about named registers
       
        * "a    : stores the data in register named a.
        * "A    : Append to the data which is already present in a register.

    To know the content of register 
        
            :reg
     
   #### Insertion
        
		 i	: to enter insert mode.
         	 I	: to start entering from the beginning of the line.
         
		 
		 f[any character]	: move to that character in the line.
		 
		 
		 a	: insert after the cursor postion.
		 A	: start appending text at the end of the line.
		 
		 
		 o	: enter insert mode on the next line.
		 O	: enter insert mode on the previous line.
		 
		 
		 J	: to join to lines.
		 
		 
		 R	: to enter replace mode
		 r	: to replace only only character without leaving the normal mode.
		 
		 
		 c	: change word.
		 EX: I love black girls.
		 		Point your cursor at black and then press cw (change word)
				and enter your text as you'll be in insert mode and then press escape.
				
		cW : change word with punctuations. 
		
		
		
		~	: to change the case of a letter.
		g~w	: change the case of a word.
		g~~	: Negate the case of entire line.
		
		
		gUw	: change the entire word after cursor position to uppercase.
		guw	: change the entire word from cursor position to uppercase.
		
		
		
  #### Repeating commands
	
		Create a line of asterisks below:
		-	80i --> you'll enter insert mode, enter * and press escape.
		
		Create 3 lines that begin with "-" below:
		-	3o --> insert mode, enter - and press escape
		
	
  #### Search Find and Replace
  	
  ###### Letter Search
	
		f{char}	: forward search that character in a line.
		F{char}	: reverse search that character in a line.
		
		t{char} : forward search till (before that character) that character in a line.
		T{char}	: reverse search till character in a line.
		
		;	: repeat in forward direction.
		,	: repeat in reverse direction.


  ###### Word Search
    		
		/{word} : forward search in the file.
		?{word}	: reverse search in the file. 
		n	: go to next match.
		N	: go to prevous match.
		
		*	: to highlight all occurance forward.
		#	: to highlight all occurance backward.


		
 ###### Substitution
    		
		:[range]s/old/new/[flags]
		
		- range can be:
					
			$		: last line.
			.		: current line.
			1s		: first line.
			1,5s/old/new/g	: 1st to 5th line.
			1,$		: 1st to last line.
			%		: Entire file.
			
			OR it can also be pattern
			
			/Global/,/Local/s/old/new/g	: from text GLobal till Local do that subtitution.
			/Local/,$s/old/new/g		: from text Local till end of the file do that 
										substitution. 
			
	Global substitution
		
		:%s/old/new/g
				

#### Note: 
	
		- set is			: incremental search
		- set hls/hlsearch	: highlight search
		- set nu			: show number
		
		To unset use no{configname}
		To toggle conginame!
