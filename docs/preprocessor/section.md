---
title: "section | Microsoft Docs"
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
  - "section_CPP"
  - "vc-pragma.section"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "pragmas, section"
  - "section (pragma)"
ms.assetid: c67215e9-2c4a-4b0f-b691-2414d2e2d96f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# section
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Crée une section dans un fichier .obj.  
  
## Syntaxe  
  
```  
  
#pragma section( "section-name" [, attributes] )  
```  
  
## Notes  
 Les termes *segment* et *section* sont interchangeables dans cette rubrique.  
  
 Une fois qu'une section est définie, elle reste valide pour le reste de la compilation.  Toutefois, vous devez utiliser [\_\_declspec\(allocate\)](../cpp/allocate.md), sinon aucun élément ne sera placé dans la section.  
  
 *section\-name* est un paramètre obligatoire qui représente le nom de la section.  Ce nom ne doit pas être en conflit avec les noms de section standard.  Consultez [\/SECTION](../build/reference/section-specify-section-attributes.md) pour obtenir la liste des noms à ne pas utiliser lorsque vous créez une section.  
  
 `attributes` est un paramètre optionnel qui se compose d'un ou plusieurs attributs séparés par des virgules que vous souhaitez assigner à la section.  Les paramètres `attributes` possibles sont les suivants :  
  
 **read \(lecture\)**  
 Permet les opérations de lecture sur les données.  
  
 **write \(écriture\)**  
 Permet les opérations d'écriture sur les données.  
  
 **execute**  
 Permet d'exécuter le code.  
  
 **shared**  
 Partage la section entre tous les processus qui chargent l'image.  
  
 **nopage**  
 Marque la section comme non paginable ; utile pour les pilotes de périphériques Win32.  
  
 **nocache**  
 Marque la section comme ne pouvant pas être mise en cache ; utile pour les pilotes de périphériques Win32.  
  
 **discard**  
 Marque la section comme ne pouvant pas être supprimée ; utile pour les pilotes de périphériques Win32.  
  
 **remove**  
 Marque la section comme non résidante en mémoire ; pilotes de périphériques virtuels \(V*x*D\) uniquement.  
  
 Si vous ne spécifiez aucun attribut, la section aura des attributs en lecture et en écriture.  
  
## Exemple  
 Dans l'exemple suivant, la première instruction identifie la section et ses attributs.  L'entier `j` n'est pas placé dans `mysec` car il n'a pas été déclaré avec `__declspec(allocate)` ; `j` est placé dans la section de données.  L'entier `i` n'est pas placé dans `mysec` en raison de son attribut de classe de stockage `__declspec(allocate)`.  
  
```  
// pragma_section.cpp  
#pragma section("mysec",read,write)  
int j = 0;  
  
__declspec(allocate("mysec"))  
int i = 0;  
  
int main(){}  
```  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)