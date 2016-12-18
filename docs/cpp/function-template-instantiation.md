---
title: "Instanciation du mod&#232;le de fonction | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "modèles de fonctions, instanciation"
  - "instanciation, modèles de fonctions"
  - "modèles, instanciation"
ms.assetid: f22a07c7-3ad1-465a-84f5-8737e274bd47
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Instanciation du mod&#232;le de fonction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsqu'un modèle de fonction est appelé pour la première fois pour chaque type, le compilateur crée une instanciation.  Chaque instanciation est une version de la fonction basée sur un modèle spécialisée pour le type.  Cette instanciation est appelée chaque fois que la fonction est utilisée pour le type.  Si vous avez plusieurs instanciations identiques, même dans différents modules, une seule copie de l'instanciation finira dans le fichier exécutable.  
  
 La conversion des arguments de fonction est autorisée dans les modèles de fonction pour toute paire argument\-paramètre où le paramètre ne dépend pas d'un argument template.  
  
 Les modèles de fonction peuvent être instanciés de manière explicite en déclarant le modèle avec un type particulier comme argument.  Par exemple, le code suivant est autorisé :  
  
```  
// function_template_instantiation.cpp  
template<class T> void f(T) { }  
  
// Instantiate f with the explicitly specified template.  
// argument 'int'  
//  
template void f<int> (int);  
  
// Instantiate f with the deduced template argument 'char'.  
template void f(char);  
int main()  
{  
}  
```  
  
## Voir aussi  
 [Modèles de fonctions](../cpp/function-templates.md)