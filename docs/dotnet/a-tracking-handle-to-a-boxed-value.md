---
title: "Handle de suivi d&#39;une valeur boxed | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "types valeur boxed, handle de suivi de"
ms.assetid: 16c92048-5b74-47d5-8eca-dfea3d38879a
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Handle de suivi d&#39;une valeur boxed
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'utilisation d'un handle de suivi pour référencer un type valeur a été modifiée entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 La conversion boxing est une particularité du système de type unifié du CLR.  Les types valeur contiennent directement leur état, tandis que les types référence sont une paire implicite : l'entité nommée est un handle vers un objet sans nom alloué sur le tas managé.  Toute initialisation ou assignation d'un type valeur à un `Object`, par exemple, requiert que le type valeur soit placé dans le tas du CLR \- c'est là que l'image d'une conversion boxing intervient \- tout d'abord en allouant la mémoire associée, puis en copiant l'état du type valeur et en retournant ensuite l'adresse de cet hybride valeur\/référence anonyme.  Donc, lorsqu'on écrit en C\#  
  
```  
object o = 1024; // C# implicit boxing  
```  
  
 il se passe beaucoup plus de choses que la simplicité du code n'en laisse voir.  La conception de C\# masque la complexité non seulement des opérations qui ont lieu de façon invisible, mais également de l'abstraction de la conversion boxing elle\-même.  Extensions managées pour C\+\+, en revanche, qui craint que cela induise un sentiment d'efficacité injustifié, le met sous les yeux de l'utilisateur en requérant une instruction explicite :  
  
```  
Object *o = __box( 1024 ); // Managed Extensions explicit boxing  
```  
  
 La conversion boxing est implicite dans [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] :  
  
```  
Object ^o = 1024; // new syntax implicit boxing  
```  
  
 Le mot clé `__box` rend un service vital au sein des Extensions managées, absent volontairement de langages tels que C\# et [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] : il fournit à la fois un vocabulaire et un handle de suivi pour manipuler directement une instance boxed sur le tas managé.  Par exemple, étudiez le court programme ci\-dessous :  
  
```  
int main() {  
   double result = 3.14159;  
   __box double * br = __box( result );  
  
   result = 2.7;   
   *br = 2.17;     
   Object * o = br;  
  
   Console::WriteLine( S"result :: {0}", result.ToString() ) ;  
   Console::WriteLine( S"result :: {0}", __box(result) ) ;  
   Console::WriteLine( S"result :: {0}", br );  
}  
```  
  
 Le code sous\-jacent généré pour les trois appels de `WriteLine` affiche les différents coûts d'accès à la valeur d'un type valeur boxed \(merci à Yves Dolce d'avoir signalé ces différences\), les lignes indiquées affichant les charges mémoire associées à chaque appel.  
  
```  
// Console::WriteLine( S"result :: {0}", result.ToString() ) ;  
ldstr      "result :: {0}"  
ldloca.s   result  // ToString overhead  
call       instance string  [mscorlib]System.Double::ToString()  // ToString overhead  
call       void [mscorlib]System.Console::WriteLine(string, object)  
  
// Console::WriteLine( S"result :: {0}", __box(result) ) ;  
Ldstr    " result :: {0}"  
ldloc.0  
box    [mscorlib]System.Double // box overhead  
call    void [mscorlib]System.Console::WriteLine(string, object)  
  
// Console::WriteLine( S"result :: {0}", br );  
ldstr    "result :: {0}"  
ldloc.0  
call     void [mscorlib]System.Console::WriteLine(string, object)  
```  
  
 Passer directement le type valeur boxed à `Console::WriteLine` élimine à la fois la conversion boxing et la nécessité d'appeler `ToString()`. Bien sûr, il existe une première conversion boxing servant à initialiser `br`, si bien qu'en réalité, nous ne gagnons rien à moins d'avoir vraiment mis `br` au travail.  
  
 Dans la nouvelle syntaxe, la prise en charge des types valeur boxed est considérablement plus élégante et plus intégrée au système de types tout en conservant sa puissance.  Par exemple, voici la traduction du petit programme précédent :  
  
```  
int main()  
{  
   double result = 3.14159;  
   double^ br = result;  
   result = 2.7;  
   *br = 2.17;  
   Object^ o = br;  
   Console::WriteLine( "result :: {0}", result.ToString() );  
   Console::WriteLine( "result :: {0}", result );  
   Console::WriteLine( "result :: {0}", br );  
}  
```  
  
## Voir aussi  
 [Types valeur et leurs comportements \(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [Comment : demander explicitement le boxing](../dotnet/how-to-explicitly-request-boxing.md)