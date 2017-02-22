---
title: "main&#160;: d&#233;marrage du programme | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vc.main.startup"
  - "_tmain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tmain (fonction)"
  - "points d'entrée, programme"
  - "main (fonction), démarrage du programme"
  - "démarrage du programme (C++)"
  - "code de démarrage, main (fonction)"
  - "wmain (fonction)"
ms.assetid: f9581cd6-93f7-4bcd-99ec-d07c3c107dd4
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# main&#160;: d&#233;marrage du programme
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une fonction spéciale nommée `main` est le point de départ de l'exécution pour tous les programmes C et [!INCLUDE[TLA#tla_cpp](../cpp/includes/tlasharptla_cpp_md.md)].  Si vous écrivez du code conforme au modèle de programmation [!INCLUDE[TLA#tla_unicode](../cpp/includes/tlasharptla_unicode_md.md)], vous pouvez utiliser `wmain`, qui est la version à caractères larges de `main`.  
  
 La fonction `main` n'est pas prédéfinie par le compilateur.  Elle doit être fournie dans le texte du programme.  
  
 La syntaxe de déclaration pour `main` est  
  
```  
int main();  
```  
  
 ou, éventuellement,  
  
```  
int main(int argc, char *argv[], char *envp[]);  
```  
  
## Section spécifique à Microsoft  
 La syntaxe de déclaration pour `wmain` est la suivante :  
  
```  
int wmain( );  
```  
  
 ou, éventuellement,  
  
```  
int wmain(int argc, wchar_t *argv[], wchar_t *envp[]);  
```  
  
 Vous pouvez également utiliser `_tmain`, qui est définie dans TCHAR.h.  `_tmain` est résolu à `main`, à moins que \_UNICODE soit défini.  Dans ce cas, `_tmain` est résolu à `wmain`.  
  
 En guise d'alternative, les fonctions `main` et `wmain` peuvent être déclarées comme retournant `void` \(aucune valeur de retour\).  Si vous déclarez `main` ou `wmain` comme retournant `void`, vous ne pouvez pas retourner de code de sortie au processus parent ou au système d'exploitation à l'aide d'une instruction [return](../cpp/return-statement-in-program-termination-cpp.md).  Pour retourner un code de sortie lorsque `main` ou `wmain` est déclaré comme `void`, vous devez utiliser la fonction [exit](../cpp/exit-function.md).  
  
## FIN de la section spécifique à Microsoft  
 Les types pour `argc` et `argv` sont définis par le langage.  Les noms `argc`, `argv` et `envp` sont traditionnels, mais ne sont pas requis par le compilateur.  Pour plus d'informations et pour obtenir un exemple, consultez [Définitions d'arguments](../cpp/argument-definitions.md).  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Utilisation de wmain au lieu de main](../cpp/using-wmain-instead-of-main.md)   
 [Restrictions relatives à la fonction main](../cpp/main-function-restrictions.md)