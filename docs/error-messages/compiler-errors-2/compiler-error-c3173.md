---
title: "Erreur du compilateur C3173 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3173"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3173"
ms.assetid: edf79e10-e8cf-4f76-8d33-ab9d05e974e9
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3173
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

incompatibilité de version dans la fusion idl  
  
 Cette erreur se produit lorsqu'un fichier objet contient un idl incorporé qui a été généré avec une version précédente du compilateur.  Le compilateur encode un numéro de version pour garantir que le compilateur qui a été utilisé pour générer le contenu idl qui est incorporé dans les fichiers .obj est le même que le compilateur qui a été utilisé pour fusionner l'idl incorporé.  
  
 Mettez à jour votre installation de Visual C\+\+ afin que tous les outils soient présents dans la dernière version disponible.