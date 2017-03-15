---
title: "Utilisation d&#39;exit ou return | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Exit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exit (fonction)"
  - "return (mot clé) (C++), utiliser pour arrêter les programmes"
ms.assetid: b5136c5c-2505-4229-8691-2a1d6a98760b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Utilisation d&#39;exit ou return
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous appelez **exit** ou exécutez une instruction `return` à partir de **main**, les objets statiques sont détruits dans l'ordre inverse de leur initialisation.  L'exemple suivant montre comment ce type d'initialisation et de nettoyage fonctionne.  
  
## Exemple  
  
```  
// using_exit_or_return1.cpp  
#include <stdio.h>  
class ShowData {  
public:  
   // Constructor opens a file.  
   ShowData( const char *szDev ) {  
   errno_t err;  
      err = fopen_s(&OutputDev, szDev, "w" );  
   }  
  
   // Destructor closes the file.  
   ~ShowData() { fclose( OutputDev ); }  
  
   // Disp function shows a string on the output device.  
   void Disp( char *szData ) {   
      fputs( szData, OutputDev );  
   }  
private:  
   FILE *OutputDev;  
};  
  
//  Define a static object of type ShowData. The output device  
//   selected is "CON" -- the standard output device.  
ShowData sd1 = "CON";  
  
//  Define another static object of type ShowData. The output  
//   is directed to a file called "HELLO.DAT"  
ShowData sd2 = "hello.dat";  
  
int main() {  
   sd1.Disp( "hello to default device\n" );  
   sd2.Disp( "hello to file hello.dat\n" );  
}  
```  
  
 Dans l'exemple précédent, les objets statiques `sd1` et `sd2` sont créés et initialisés avant l'entrée dans `main`.  Une fois ce programme terminé avec l'instruction `return`, le premier objet `sd2` est détruit, puis `sd1`.  Le destructeur de la classe `ShowData` ferme les fichiers associés à ces objets statiques. \(Pour plus d'informations sur l'initialisation, les constructeurs et les destructeurs, consultez [Fonctions membres spéciales](../misc/special-member-functions-cpp.md).\)  
  
 Une autre façon d'écrire ce code consiste à déclarer les objets `ShowData` avec portée de bloc, ce qui permet leur description lorsqu'ils sont hors de portée :  
  
```  
int main() {  
   ShowData sd1, sd2( "hello.dat" );  
  
   sd1.Disp( "hello to default device\n" );  
   sd2.Disp( "hello to file hello.dat\n" );  
}  
```  
  
## Voir aussi  
 [Considérations supplémentaires sur la terminaison](../cpp/additional-termination-considerations.md)