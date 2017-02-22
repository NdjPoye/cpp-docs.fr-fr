---
title: "Erreur irr&#233;cup&#233;rable C1905 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1905"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1905"
ms.assetid: fefc6769-477f-45a2-9878-6f0a5f42472c
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur irr&#233;cup&#233;rable C1905
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Front\-end et back end non compatibles \(doivent cibler le même processeur\)  
  
 Cette erreur se produit quand un fichier .obj est généré par un compilateur frontal \(C1.dll\) qui cible un processeur, tel que x86, ARM ou [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)], mais qui est lu par un compilateur principal \(C2.dll\) qui cible un processeur différent.  
  
 Pour résoudre ce problème, assurez\-vous d'utiliser un compilateur frontal et un compilateur principal qui correspondent.  Il s'agit du paramétrage par défaut pour les projets créés dans Visual Studio.  Cette erreur peut se produire si vous avez modifié le fichier projet et utilisé des chemins d'accès aux outils de compilateur différents.  Si vous n'avez pas spécifiquement défini de chemin d'accès pour les outils du compilateur, cette erreur peut survenir si votre installation de Visual Studio est endommagée.  Par exemple, vous pouvez avoir copié les fichiers .dll du compilateur d'un emplacement à un autre.  Utilisez **Programmes et fonctionnalités** dans le panneau de configuration Windows pour réparer ou réinstaller Visual Studio.