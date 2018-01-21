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
     
            
 
    
                  
       
                  
