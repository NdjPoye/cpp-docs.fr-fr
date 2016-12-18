---
title: "D&#233;tails de la prise en charge ATL ajout&#233;e par l&#39;Assistant ATL | Microsoft Docs"
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
  - "vc.codewiz.atl.support"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, projets MFC"
  - "MFC, prise en charge ATL"
ms.assetid: aa66bad0-008f-4886-94c1-2a0a0d04bce4
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;tails de la prise en charge ATL ajout&#233;e par l&#39;Assistant ATL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Si vous [ajoutez la prise en charge ATL à un exécutable MFC ou à une DLL](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), Visual C\+\+ apporte les modifications suivantes au projet MFC existant \(dans cet exemple, le projet est appelé `MFCEXE`\) :  
  
-   Deux nouveaux fichiers \(un fichier .idl et un fichier .rgs, utilisés pour inscrire le serveur\) sont ajoutés.  
  
-   Dans l'en\-tête de l'application principale et dans les fichiers d'implémentation \(Mfcexe.h et Mfcexe.cpp\), une nouvelle classe \(dérivée de **CAtlMFCModule**\) est ajoutée.  Outre la nouvelle classe, du code est ajouté à `InitInstance` pour l'inscription.  Du code est également ajouté à la fonction `ExitInstance` pour révoquer l'objet de classe.  Enfin, dans le fichier d'en\-tête, deux nouveaux fichiers d'en\-tête \(Initguid.h et Mfcexe\_i.c\) sont ajoutés au fichier d'implémentation, déclarant et initialisant les nouveaux identificateurs universels uniques \(GUID, Globally Unique ID\) pour la classe dérivée de **CAtlMFCModule**.  
  
-   Pour inscrire correctement le serveur, une entrée correspondant au nouveau fichier .rgs est ajoutée au fichier de ressources du projet.  
  
## Remarques relatives aux projets DLL  
 Si vous ajoutez la prise en charge ATL à un projet DLL MFC, vous pouvez constater certaines différences.  Du code est ajouté aux fonctions **DLLRegisterServer** et **DLLUnregisterServer** pour l'inscription et la désinscription de la DLL.  Du code est également ajouté à [DllCanUnloadNow](../Topic/CAtlDllModuleT::DllCanUnloadNow.md) et à [DllGetClassObject](../Topic/CAtlDllModuleT::DllGetClassObject.md).  
  
## Voir aussi  
 [Prise en charge ATL dans un projet MFC](../../mfc/reference/adding-atl-support-to-your-mfc-project.md)   
 [Ajout de fonctionnalités à l'aide des Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Ajout d'une classe](../../ide/adding-a-class-visual-cpp.md)   
 [Ajout d'une fonction membre](../../ide/adding-a-member-function-visual-cpp.md)   
 [Ajout d'une variable membre](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Substitution d'une fonction virtuelle](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC, gestionnaire de messages](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Parcours de la structure de classe](../../ide/navigating-the-class-structure-visual-cpp.md)