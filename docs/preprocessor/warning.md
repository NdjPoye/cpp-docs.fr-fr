---
title: "warning | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "warning_CPP"
  - "vc-pragma.warning"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pop warning (pragma)"
  - "pragmas, warning"
  - "push (pragma) warning"
  - "warning (pragma)"
ms.assetid: 8e9a0dec-e223-4657-b21d-5417ebe29cc8
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# warning
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Active la modification sélective du comportement des messages d'avertissement du compilateur.  
  
## Syntaxe  
  
```  
  
      #pragma warning(   
      warning-specifier  
       :   
      warning-number-list [; warning-specifier : warning-number-list...] )  
#pragma warning( push[ ,n ] )  
#pragma warning( pop )  
```  
  
## Notes  
 Les paramètres spécificateur\-avertissement suivants sont disponibles.  
  
|spécificateur\-avertissement|Signification|  
|----------------------------------|-------------------|  
|`1, 2, 3, 4`|Applique le niveau donné du ou des avertissements spécifiés.  Cela active également un avertissement spécifié qui est désactivé par défaut.|  
|`default`|Réinitialise le comportement d'avertissement à sa valeur par défaut.  Cela active également un avertissement spécifié qui est désactivé par défaut.  L'avertissement est généré à son niveau par défaut, documenté.<br /><br /> Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../preprocessor/compiler-warnings-that-are-off-by-default.md).|  
|`disable`|Ne publie pas le ou les messages d'avertissement spécifiés.|  
|`error`|Signale les avertissements spécifiés comme des erreurs.|  
|`once`|Affiche le ou les messages spécifiés une seule fois.|  
|`suppress`|Exécute un push de l'état actuel du pragma sur la pile, désactive l'avertissement spécifié pour la ligne suivante, puis dépile la pile d'avertissement afin que l'état pragma soit réinitialisé.|  
  
 L'instruction de code suivante montre qu'un paramètre `warning-number-list` peut contenir plusieurs numéros d'avertissement, et que plusieurs paramètres `warning-specifier` peuvent être spécifiés dans la même directive pragma.  
  
```  
#pragma warning( disable : 4507 34; once : 4385; error : 164 )  
```  
  
 Cela équivaut fonctionnellement au code suivant.  
  
```  
// Disable warning messages 4507 and 4034.  
#pragma warning( disable : 4507 34 )  
  
// Issue warning 4385 only once.  
#pragma warning( once : 4385 )  
  
// Report warning 4164 as an error.  
#pragma warning( error : 164 )  
```  
  
 Le compilateur ajoute 4000 à n'importe quel numéro d'avertissement compris entre 0 et 999.  
  
 Pour les numéros d'avertissement dans la plage 4700\-4999 qui sont associés à la génération du code, l'état d'avertissement en vigueur lorsque le compilateur rencontre l'accolade ouvrante d'une fonction est appliquée pour le reste de la fonction.  L'utilisation du pragma `warning` dans la fonction pour modifier l'état d'un avertissement qui a un nombre supérieur à 4699 entre en vigueur uniquement après la fin de la fonction.  L'exemple suivant indique le positionnement correct des pragmas `warning` pour désactiver un message d'avertissement génération\-code, puis pour le restaurer.  
  
```  
// pragma_warning.cpp  
// compile with: /W1  
#pragma warning(disable:4700)  
void Test() {  
   int x;  
   int y = x;   // no C4700 here  
   #pragma warning(default:4700)   // C4700 enabled after Test ends  
}  
  
int main() {  
   int x;  
   int y = x;   // C4700  
}  
```  
  
 Notez que partout dans un corps de la fonction, le dernier paramètre du pragma `warning` sera appliqué à la fonction entière.  
  
## Push et pop  
 Le pragma `warning` prend également en charge la syntaxe suivante.  
  
 `#pragma warning(` `push` \[ `,``n` \] `)`  
  
 `#pragma warning(` `pop )`  
  
 Où `n` représente un niveau d'avertissement \(1 à 4\).  
  
 Le pragma `warning( push )` stocke l'état actuel d'avertissement pour chaque avertissement.  Le pragma `warning( push,` `n``)` stocke l'état actuel pour chaque avertissement et définit le niveau d'avertissement global sur `n`.  
  
 Le pragma `warning( pop )` dépile le dernier état d'avertissement ayant fait l'objet d'un push dans la pile.  Toutes les modifications apportées à l'état d'avertissement entre `push` et `pop` sont annulées.  Considérez cet exemple :  
  
```  
#pragma warning( push )  
#pragma warning( disable : 4705 )  
#pragma warning( disable : 4706 )  
#pragma warning( disable : 4707 )  
// Some code  
#pragma warning( pop )   
```  
  
 À la fin de ce code, `pop` restaure l'état de chaque avertissement \(inclut 4705, 4706 et 4707\) à ce qu'il était au début du code.  
  
 Lorsque vous écrivez des fichiers d'en\-tête, vous pouvez utiliser `push` et `pop` pour garantir que les modifications de type état\-avertissement apportées par un utilisateur n'empêchent pas les en\-têtes de se compiler correctement.  Utilisez `push` au début de l'en\-tête et `pop` à la fin.  Par exemple, si vous avez un en\-tête qui ne se compile pas correctement au niveau de l'avertissement 4, le code suivant remplace le niveau d'avertissement par 3, puis restaure le niveau d'avertissement d'origine à la fin de l'en\-tête.  
  
```  
#pragma warning( push, 3 )  
// Declarations/definitions  
#pragma warning( pop )   
```  
  
 Pour plus d'informations sur les options du compilateur qui vous aident à supprimer des avertissements, consultez [\/FI](../build/reference/fi-name-forced-include-file.md) et [\/w](../build/reference/compiler-option-warning-level.md).  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)