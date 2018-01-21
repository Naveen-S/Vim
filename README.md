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
    
                  
            dd  : delete an entire line.
            d$  : delete till end of the line.
            
            dG  : delete till end of the file.
            dgg : delete from cursor position to start of the file.
       
                  
