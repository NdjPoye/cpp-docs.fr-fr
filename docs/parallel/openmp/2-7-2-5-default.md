---
title: "2.7.2.5 default | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: c856df07-705c-4ad3-9105-a268dd33e939
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.2.5 default
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La clause de **valeur par défaut** permet à l'utilisateur d'affecter les attributs de partage de données des variables.  La syntaxe de la clause de **valeur par défaut** est la suivante :  
  
```  
default(shared | none)  
```  
  
 Spécifier **valeur par défaut \(partagé\)** équivaut à répertorier explicitement chaque variable actuellement visible dans une clause de **partagé** , à moins qu'il ne **threadprivate** ou **cons**`t`\- qualifié.  En l ' absence d'une clause explicite de **valeur par défaut** , le comportement par défaut est le même que si **valeur par défaut \(partagé\)** ont été spécifiés.  
  
 Spécifiant **valeur par défaut \(sans\)** exige qu'au moins l'une des conditions suivantes doivent être remplies pour chaque référence à une variable dans l'étendue lexicale de l'élément parallèle :  
  
-   La variable est explicitement répertorié dans une clause d'attribut de partage de données d'un élément qui contient la référence.  
  
-   la variable est déclarée dans l'élément parallèle.  
  
-   la variable est **threadprivate**.  
  
-   la variable a **const**\- type qualifié.  
  
-   la variable est la variable de contrôle de boucle pour une boucle de **pour** qui suit immédiatement une directive de **pour** ou de **parallèle pour** , et la référence variable apparaît à l'intérieur de la boucle.  
  
 spécifiant une variable sur **firstprivate**, **elle**, ou la clause de **réduction** d'une directive placé entre provoque une référence implicite à la variable dans le contexte englobant.  De telles références implicites sont soumises également aux spécifications répertoriées ci\-dessus.  
  
 Uniquement une clause unique de **valeur par défaut** peut être spécifiée dans une directive de **parallèle** .  
  
 L'attribut par défaut de la partage de données d'une variable peut être substituée à l'aide de **privé**, de **firstprivate**, d' **elle**, de **réduction**, les clauses de **partagé** , comme le montre l'exemple suivant :  
  
```  
#pragma  omp  parallel  for  default(shared)  firstprivate(i)\  
   private(x)  private(r)  lastprivate(i)  
```