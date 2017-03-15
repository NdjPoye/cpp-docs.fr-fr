---
title: "Noms du contr&#244;le, Assistant Contr&#244;le ActiveX&#160;MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.ctl.names"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Contrôle ActiveX MFC, noms des contrôles"
ms.assetid: 9b8b81d2-36df-48ed-b58a-a771a0e269ee
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Noms du contr&#244;le, Assistant Contr&#244;le ActiveX&#160;MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifiez les noms de la classe du contrôle et de la classe de la page de propriétés, ainsi que les noms et les identificateurs de type pour votre contrôle.  À l'exception du champ **Nom court**, tous les autres champs peuvent être modifiés de manière indépendante.  Si vous changez le texte du champ **Nom court**, la modification est répercutée sur les noms de tous les autres champs de cette page.  Ce mode d'affectation des noms est destiné à faciliter l'identification de tous les noms lorsque vous développez votre contrôle.  
  
 **Nom court**  
 Spécifiez une abréviation pour le nom du contrôle.  Par défaut, ce nom est défini sur la base du nom de projet que vous avez spécifié dans la boîte de dialogue **Nouveau projet**.  Le nom indiqué dans ce champ détermine les noms des classes, les noms des types et les identificateurs des types, à moins que vous ne modifiiez manuellement les champs correspondants.  
  
 **Nom de la classe du contrôle**  
 Par défaut, le nom de la classe du contrôle est défini à partir du nom court, auquel sont ajoutés le préfixe `C` et le suffixe `Ctrl`.  Par exemple, si le nom court de votre contrôle est `Price`, le nom de la classe du contrôle est `CPriceCtrl`.  
  
 **Fichier .h du contrôle**  
 Par défaut, le nom du fichier d'en\-tête est défini à partir du nom court, auquel sont ajoutés le suffixe `Ctrl` et l'extension de fichier `.h`.  Par exemple, si le nom court de votre contrôle est `Price`, le nom du fichier d'en\-tête est `PriceCtrl.h`.  Le nom indiqué dans ce champ doit correspondre au nom de la classe du contrôle.  
  
 **Fichier .cpp du contrôle**  
 Par défaut, le nom du fichier d'en\-tête est défini à partir du nom court, auquel sont ajoutés le suffixe `Ctrl` et l'extension de fichier `.cpp`.  Par exemple, si le nom court de votre contrôle est `Price`, le nom du fichier d'en\-tête est `PriceCtrl.cpp`.  Le nom indiqué dans ce champ doit correspondre au nom de l'en\-tête.  
  
 **Type du contrôle**  
 Par défaut, le nom du type du contrôle est défini à partir du nom court, suivi de `Control`.  Par exemple, si le nom court de votre contrôle est `Price`, le nom de la classe du contrôle est `Price Control`.  Si vous changez la valeur de ce champ, veillez à ce que le nom indique une relation d'héritage.  
  
 **ID du type du contrôle**  
 Définit l'ID du type du contrôle pour la classe du contrôle.  Cette chaîne est consignée par le contrôle dans le Registre lors de son ajout au projet.  Elle est utilisée par les applications conteneurs pour créer une instance du contrôle.  
  
 Par défaut, l'ID du type du contrôle est défini en fonction du nom de projet, que vous avez spécifié dans la boîte de dialogue **Nouveau projet**, et du nom court.  Ce nom doit correspondre au nom du type.  
  
 Par défaut, l'ID du type du contrôle est défini comme suit :  
  
 *ProjectName*.*ShortName*Ctrl.1  
  
 Si vous modifiez le nom court dans cette boîte de dialogue, l'ID du type du contrôle devient :  
  
 *ProjectName*.*NewShortName*Ctrl.1  
  
 **Nom de la classe de page de prop.**  
 Par défaut, le nom de la classe de la page de propriétés est défini à partir du nom court, auquel sont ajoutés le préfixe `C` et le suffixe `PropPage`.  Par exemple, si le nom court de votre contrôle est `Price`, le nom de la classe de la page de propriétés est `CPricePropPage`.  Ce nom doit correspondre au nom de la classe du contrôle, à l'exception du suffixe `PropPage`.  
  
 **Fichier .h de page de prop.**  
 Par défaut, le nom du fichier d'en\-tête pour la page de propriétés est défini à partir du nom court, auquel sont ajoutés le suffixe `PropPage` et l'extension de fichier `.h`.  Par exemple, si le nom court de votre contrôle est `Price`, le nom du fichier d'en\-tête pour la page de propriétés est `PricePropPage.h`.  Ce nom doit correspondre au nom de la classe.  
  
 **Fichier .cpp de page de prop.**  
 Par défaut, le nom du fichier d'implémentation pour la page de propriétés est défini à partir du nom court, auquel sont ajoutés le suffixe `PropPage` et l'extension de fichier `.cpp`.  Par exemple, si le nom court de votre contrôle est `Price`, le nom du fichier d'en\-tête pour la page de propriétés est `PricePropPage.cpp`.  Ce nom doit correspondre au nom du fichier d'en\-tête.  
  
 **Type de classe pg. de prop.**  
 Par défaut, le nom du type de la page de propriétés est défini à partir du nom court, suivi de `Property Page`.  Par exemple, si le nom court de votre contrôle est `Price`, le nom du type de la page de propriétés est `Price Property Page`.  Si vous changez la valeur de ce champ, veillez à ce que le nom indique la classe du contrôle.  
  
 **ID du type de page de prop.**  
 Définit l'ID de la classe pour la page de propriétés.  Cette chaîne est consignée par le contrôle dans le Registre lors de son ajout au projet.  Elle est utilisée par les applications conteneurs pour créer une instance de la page de propriétés du contrôle.  
  
 Par défaut, l'ID du type de la page de propriétés est défini en fonction du nom de projet, que vous avez spécifié dans la boîte de dialogue **Nouveau projet**, et du nom court.  Ce nom doit correspondre au nom du type.  
  
 Par défaut, l'ID du type de la page de propriétés est défini comme suit :  
  
 *ProjectName*.*ShortName*PropPage.1  
  
 Si vous modifiez le nom court dans cette boîte de dialogue, l'ID du type de la page de propriétés devient :  
  
 *ProjectName*.*NewShortName*PropPage.1  
  
## Voir aussi  
 [Contrôle ActiveX MFC \(Assistant\)](../../mfc/reference/mfc-activex-control-wizard.md)   
 [Paramètres de l’application, Assistant Contrôle ActiveX MFC](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)   
 [Paramètres du contrôle, Assistant Contrôle ActiveX MFC](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)   
 [Types de fichiers créés pour les projets Visual C\+\+](../../ide/file-types-created-for-visual-cpp-projects.md)