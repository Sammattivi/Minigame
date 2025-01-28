program FIrstMinigame;
var
ran, tries, guess, choice, rec:integer;
highscore:text;
Nome:string;
begin
  repeat
  writeln('Escolhe o Numero: 1 para jogar, 2 para ver o highscore e 3 para sair');
  readln(choice);
  case choice of
    1:begin
       randomize;
       ran:=random(10000);
       tries:=0;
       write(ran);
       writeln('da um numero entre 0 e 10000:');
       repeat
         tries:=tries+1;
         readln(guess);

         if guess<ran then
           writeln('o numero e maior do que ',guess)
         else if guess>ran then
             writeln('o numero e menor do que ',guess)
           else
             writeln('correto');
       until guess=ran;
       writeln('usou ',tries,' tentativas.');

       assign(highscore, 'recorde.txt');
       reset(highscore);
       readln(highscore, Nome);
       readln(highscore, rec);
       close(highscore);
       if tries<rec then begin
         rec:=tries;
         assign(highscore, 'recorde.txt');
         rewrite(highscore);
         writeln('Qual e o seu Username?');
         readln(nome);
         writeln(highscore, Nome);
         writeln(highscore, rec);
         close(highscore);
       end;
     end;
    2:begin
        assign(highscore, 'recorde.txt');
        reset(highscore);
        readln(highscore, Nome);
        writeln('o user e: ', Nome);
        readln(highscore, rec);
        writeln('E o highscore e ', rec ,' tentativas');
        close(highscore);
     end;

    end;

    until choice=3 ;

end. 
