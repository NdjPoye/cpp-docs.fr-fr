---
title: "Probl&#232;mes de version pour les types valeur imbriqu&#233;s dans les types natifs (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "_nogc (déclarations de type)"
  - "__value (mot clé), problèmes lors de l'imbrication"
ms.assetid: 0a3b1a43-39c6-4b52-be2f-1074690188aa
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Probl&#232;mes de version pour les types valeur imbriqu&#233;s dans les types natifs (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Considérez un composant d'assembly signé \(nom fort\) utilisé pour générer un assembly client.  Le composant contient un type valeur utilisé dans le client en tant que type d'un membre d'une union native, une classe ou un tableau.  Si une version future du composant modifie la taille ou la présentation du type valeur, le client devra être recompilé.  
  
 Créez un keyfile avec [sn.exe](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md) \(`sn -k mykey.snk`\).  
  
## Exemple  
 L'exemple suivant est le composant.  
  
```  
// nested_value_types.cpp  
// compile with: /clr /LD  
using namespace System::Reflection;  
[assembly:AssemblyVersion("1.0.0.*"),   
assembly:AssemblyKeyFile("mykey.snk")];  
  
public value struct S {  
   int i;  
   void Test() {  
      System::Console::WriteLine("S.i = {0}", i);  
   }  
};  
```  
  
## Exemple  
 Voici l'exemple client :  
  
```  
// nested_value_types_2.cpp  
// compile with: /clr  
#using <nested_value_types.dll>  
  
struct S2 {  
   S MyS1, MyS2;  
};  
  
int main() {  
   S2 MyS2a, MyS2b;  
   MyS2a.MyS1.i = 5;  
   MyS2a.MyS2.i = 6;  
   MyS2b.MyS1.i = 10;  
   MyS2b.MyS2.i = 11;  
  
   MyS2a.MyS1.Test();  
   MyS2a.MyS2.Test();  
   MyS2b.MyS1.Test();  
   MyS2b.MyS2.Test();  
}  
```  
  
## Sortie  
  
```  
S.i = 5  
S.i = 6  
S.i = 10  
S.i = 11  
```  
  
### Commentaires  
 Toutefois, si vous ajoutez un autre membre à `struct S` dans nested\_value\_types.cpp, \(par exemple, `double d;`\) et si vous recompilez le composant sans recompiler le client, le résultat est une exception non gérée \(de type <xref:System.IO.FileLoadException?displayProperty=fullName>\).  
  
## Voir aussi  
 [Types managés](../dotnet/managed-types-cpp-cli.md)