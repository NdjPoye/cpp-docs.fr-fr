---
title: "Erreurs potentielles de passage d&#39;objets CRT entre fronti&#232;res DLL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conflits DLL (C++)"
ms.assetid: c217ffd2-5d9a-4678-a1df-62a637a96460
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreurs potentielles de passage d&#39;objets CRT entre fronti&#232;res DLL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous passez des objets C Run\-time comme des gestionnaires de fichiers ou des variables locales ou d'environnement en entrant ou sortant d'un DDL \(la fonction appelle des variables en dehors des frontières du DDL\), un comportement inattendu peut se produire si le DDL, ainsi que les fichiers appelant à l'intérieur du DDL, utilisent différentes copies des librairies CRT.  
  
 Un problème relatif peut se produire lorsque vous allouez de la mémoire \(soit explicitement avec `new` ou `malloc`, soit implicitement avec `strdup`, `strstreambuf::str`, etc.\) puis passez un pointeur sur une limite de la DLL à récupérer.  Cela peut entraîner une violation d'accès de mémoire ou l'altération d'un segment si la DLL et ses utilisateurs utilisent des copies différentes des bibliothèques CRT.  
  
 Un autre symptôme de ce problème peut être une erreur dans la fenêtre Sortie pendant le débogage telle que :  
  
 HEAP \[\] : Adresse Invalide spécifiée à RtlValidateHeap \(\#, \#\)  
  
## Causes  
 Chaque copie de la bibliothèque CRT possède un état séparé et bien distinct.  Par conséquent, le s objets CRT  tels que les descripteurs de fichiers, les variables d'environnement, ou locales sont uniquement valides pour la copie de la CRT où ces objets sont affectés ou définis.  Lorsqu'une DLL et ses utilisateurs utilisent des copies de la bibliothèque CRT, vous ne pouvez pas passer ces objets CRT à travers de la limite du DLL et vous attendre à ce qu'ils soient pris correctement en sortie.  
  
 En outre, chaque copie de la bibliothèque CRT a son propre gestionnaire de segment, l'allocation mémoire dans une bibliothèque CRT et le fait de passer le pointeur à travers une limite de la DLL pour qu'il soit libéré par une autre copie de la bibliothèque CRT est une cause potentielle de corruption du segment.  
  
 Si vous concevez votre DLL pour qu'il passe des objets CRT à travers la limite ou alloue de la mémoire et s'attend à ce qu'elle soit libéré en dehors de la DLL, vous limitez les utilisateurs de la DLL à utiliser la même sauvegarde de la bibliothèque CRT comme DLL.  La DLL et ses utilisateurs utilisent la même copie de la bibliothèque CRT uniquement si les deux sont liés à la même version de la DLL CRT.  Cela peut être un problème si vous combinez des applications établies avec Visual C\+\+ 5,0 avec les DLL générés par Visual C\+\+ 4.1 ou une de ses versions antérieures.  Étant donné que la version de DLL de la librairie CRT utilisée par Visual C\+\+ 4.1 est msvcrt40.dll et celle utilisée par Visual basic 5,0 est msvcrt.dll, vous ne pouvez pas créer une application, qui utilise la même sauvegarde de la bibliothèque CRT que les DLL.  
  
 Mais il existe une exception.  Dans la version en anglais américain et dans d'autres versions localisées de Windows 2000, telles que l'Allemand, Français, et le Tchèque, une version redirecteur de msvcrt40.dll \(version 4,20\) est expédiée.  Par conséquent, même si la DLL est liée à msvcrt40.dll et l'utilisateur est lié à msvcrt.dll, vous utilisez toujours la même copie de la bibliothèque CRT car tous les appels effectués auprès de msvcrt40.dll sont transférés à msvcrt.dll.  
  
 Toutefois cette version redirecteur de msvcrt40.dll n'est pas disponible dans les versions localisées de Windows 2000, telle que le Japonais, Coréen, et en Chinois.  Par conséquent, si votre application cible ces systèmes d'exploitation, vous devez soit obtenir une version mise à jour de la DLL qui ne s'appuie pas sur msvcrt40.dll ou modifiez votre application, afin qu'elle ne s'appuie pas sur la meme copie des librairies CRT.   Si vous avez développé la DLL, cela signifie le recréer avec Visual C\+\+ 4,2 ou une version ultérieure.  S'il s'agit d'une DLL tiers, vous devez contacter votre fournisseur pour obtenir une mise à niveau.  
  
 Notez que cette version de DLL redirecteur de msvcrt40.dll \(version 4,20\) ne peut pas être redistribuée.  
  
## Exemple  
  
### Description  
 Cet exemple passe un gestionnaire de fichier à travers la limite d'un DDL.  
  
 La DLL et le fichier .exe sont générés avec \/MD, ils partagent une seule copie de la CRT.  
  
 Si vous reconstruisez avec \/MT afin qu'ils utilisent des copies distinctes de la CRT, l'exécution du test1Main.exe résultant provoque une violation d'accès.  
  
### Code  
  
```  
// test1Dll.cpp  
// compile with: /MD /LD  
#include <stdio.h>  
__declspec(dllexport) void writeFile(FILE *stream)  
{  
   char   s[] = "this is a string\n";  
   fprintf( stream, "%s", s );  
   fclose( stream );  
}  
```  
  
### Code  
  
```  
// test1Main.cpp  
// compile with: /MD test1dll.lib  
#include <stdio.h>  
#include <process.h>  
void writeFile(FILE *stream);  
  
int main(void)  
{  
   FILE  * stream;  
   errno_t err = fopen_s( &stream, "fprintf.out", "w" );  
   writeFile(stream);  
   system( "type fprintf.out" );  
}  
```  
  
### Sortie  
  
```  
this is a string  
```  
  
## Exemple  
  
### Description  
 Cet exemple passe des variables d'environnement à travers une limite DDL.  
  
### Code  
  
```  
// test2Dll.cpp  
// compile with: /MT /LD  
#include <stdio.h>  
#include <stdlib.h>  
  
__declspec(dllexport) void readEnv()  
{  
   char *libvar;  
   size_t libvarsize;  
  
   /* Get the value of the MYLIB environment variable. */   
   _dupenv_s( &libvar, &libvarsize, "MYLIB" );  
  
   if( libvar != NULL )  
      printf( "New MYLIB variable is: %s\n", libvar);  
   else  
      printf( "MYLIB has not been set.\n");  
   free( libvar );  
}  
```  
  
### Code  
  
```  
// test2Main.cpp  
// compile with: /MT /link test2dll.lib  
#include <stdlib.h>  
#include <stdio.h>  
  
void readEnv();  
  
int main( void )  
{  
   _putenv( "MYLIB=c:\\mylib;c:\\yourlib" );  
   readEnv();  
}  
```  
  
### Sortie  
  
```  
MYLIB has not been set.  
```  
  
 Si la DLL et le fichier .exe sont générés tous les deux avec \/MD afin qu'une seule copie de la CRT soit utilisée, le programme s'exécute avec succès et produit la sortie suivante :  
  
```  
New MYLIB variable is: c:\mylib;c:\yourlib  
```  
  
## Voir aussi  
 [Fonctions de bibliothèque CRT](../c-runtime-library/crt-library-features.md)