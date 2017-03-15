---
title: "Avertissement du compilateur (niveau 1) C4819 | Microsoft Docs"
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
  - "C4819"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4819"
ms.assetid: c0316e85-249c-414d-9df0-622d077c6bc2
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4819
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le fichier contient un caractère qui ne peut pas être représenté dans la page de codes actuelle \(numéro\).Enregistrez le fichier au format Unicode pour éviter toute perte de données.  
  
 L'erreur C4819 se produit quand un fichier source ANSI est compilé sur un système avec une page de codes qui ne peut pas représenter tous les caractères compris dans le fichier.  
  
 Pour résoudre l'erreur C4819, enregistrez le fichier au format Unicode.  Dans Visual Studio, choisissez **Fichier**, **Options d'enregistrement avancées**.  Dans la boîte de dialogue **Options d'enregistrement avancées**, sélectionnez un encodage qui peut représenter tous les caractères compris dans le fichier \(par exemple, UTF\-8\), puis choisissez **OK**.