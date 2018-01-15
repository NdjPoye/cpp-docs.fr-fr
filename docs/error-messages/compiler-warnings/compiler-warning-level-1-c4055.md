# <a name="compiler-warning-level-1-c4055"></a>Avertissement du compilateur (niveau 1) C4055  
  
'conversion' : du pointeur donnée 'type1' en pointeur fonction 'type2'  
  
**Obsolète :** cet avertissement n’est pas généré par Visual Studio 2017 et versions ultérieures.

 Un pointeur donnée est converti (peut-être de façon incorrecte) en un pointeur fonction. Il s’agit d’un avertissement de niveau 1 sous /Za et d’un avertissement de niveau 4 sous /Ze.  
  
 L’exemple suivant génère l’avertissement C4055 :  
  
```C  
// C4055.c  
// compile with: /Za /W1 /c  
typedef int (*PFUNC)();  
int *pi;  
PFUNC f() {  
   return (PFUNC)pi;   // C4055  
}  
```  
  
 Sous /Ze, il s’agit d’un avertissement de niveau 4.  
  
```C  
// C4055b.c  
// compile with: /W4 /c  
typedef int (*PFUNC)();  
int *pi;  
PFUNC f() {  
return (PFUNC)pi;   // C4055  
}  
```