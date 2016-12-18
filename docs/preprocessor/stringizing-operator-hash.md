---
title: "Op&#233;rateur d&#39;encha&#238;nement (#) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "# (opérateur de préprocesseur)"
  - "arguments (C++), convertir en chaînes"
  - "macros (C++), convertir les paramètres en chaînes"
  - "préprocesseur"
  - "préprocesseur, opérateurs"
  - "littéraux de chaîne, convertir les paramètres macro en"
  - "opérateur d'enchaînement"
ms.assetid: 1175dd19-4538-43b3-ad97-a008ab80e7b1
caps.latest.revision: 16
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Op&#233;rateur d&#39;encha&#238;nement (#)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le signe dièse ou opérateur de « chaîne » \(**\#**\) convertit des paramètres de macro en littéraux de chaîne sans développer la définition des paramètres.  Il est utilisé uniquement avec les macros qui acceptent des arguments.  S'il précède un paramètre formel dans la définition de la macro, l'argument réel passé par l'appel de macro est entre guillemets et traité en tant que littéral de chaîne.  Le littéral de chaîne remplace alors chaque occurrence d'une combinaison de l'opérateur de chaîne et du paramètre formel dans la définition de macro.  
  
> [!NOTE]
>  L'extension Microsoft C \(versions 6.0 et antérieures\) de la norme C ANSI, qui développait auparavant les arguments formels de macro apparaissant dans les littéraux de chaîne et les constantes caractère, n'est plus prise en charge.  Le code qui reposait sur cette extension doit être réécrit à l'aide de l'opérateur de chaîne \(**\#**\).  
  
 L'espace blanc qui précède le premier jeton de l'argument réel ou qui suit le dernier jeton de l'argument réel est ignoré.  Tout espace blanc situé entre les jetons dans l'argument réel est réduit à un espace blanc unique dans le littéral de chaîne résultant.  Ainsi, si un commentaire figure entre deux jetons de l'argument réel, il est réduit à un espace blanc unique.  Le littéral de chaîne résultant est automatiquement concaténé avec tous les littéraux de chaîne adjacents dont il est séparé uniquement par un espace blanc.  
  
 De plus, si un caractère inclus dans l'argument requiert généralement une séquence d'échappement lorsqu'il est utilisé dans un littéral de chaîne \(par exemple, un guillemet \(**"**\) ou une barre oblique inverse \(**\\**\)\), la barre oblique inverse d'échappement requise est automatiquement insérée avant ce caractère.  
  
 L'opérateur de chaîne Visual C\+\+ peut ne pas fonctionner comme prévu dans toutes les situations. Consultez [16.3.2 L'opérateur \#](../misc/16-3-2-the-hash-operator.md) pour plus d'informations.  
  
## Exemple  
 L'exemple ci\-dessous illustre une définition de macro incluant l'opérateur de chaîne et une fonction principale qui appelle la macro :  
  
 Ces appels sont développés pendant le prétraitement et génèrent le code suivant :  
  
```  
int main() {  
   printf_s( "In quotes in the printf function call\n" "\n" );  
   printf_s( "\"In quotes when printed to the screen\"\n" "\n" );  
   printf_s( "\"This: \\\" prints an escaped double quote\"" "\n" );  
}  
```  
  
```  
// stringizer.cpp  
#include <stdio.h>  
#define stringer( x ) printf_s( #x "\n" )  
int main() {  
   stringer( In quotes in the printf function call );   
   stringer( "In quotes when printed to the screen" );     
   stringer( "This: \"  prints an escaped double quote" );  
}  
```  
  
  **In quotes in the printf function call**  
**"In quotes when printed to the screen"**  
**"This: \\"  prints an escaped double quote"**   
## Exemple  
 L'exemple suivant montre comment développer un paramètre de macro :  
  
```  
// stringizer_2.cpp  
// compile with: /E  
#define F abc  
#define B def  
#define FB(arg) #arg  
#define FB1(arg) FB(arg)  
FB(F B)  
FB1(F B)  
```  
  
## Voir aussi  
 [Opérateurs de préprocesseur](../preprocessor/preprocessor-operators.md)