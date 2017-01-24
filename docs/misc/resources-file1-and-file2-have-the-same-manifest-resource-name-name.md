---
title: "Resources &#39;file1&#39; and &#39;file2&#39; have the same manifest resource name &#39;name&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.resource_naming_conflict"
ms.assetid: 50d656ad-8557-4240-95b0-3f44b9c21da6
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Resources &#39;file1&#39; and &#39;file2&#39; have the same manifest resource name &#39;name&#39;
Le système de projet a défini des noms de ressources de l'assembly identiques pour deux fichiers dont la propriété `BuildAction` a la valeur `EmbeddedResource` et qui ont une culture neutre.  Le processus de génération échoue si cette erreur se produit.  Pour plus d'informations sur la propriété `BuildAction`, consultez [File Properties](http://msdn.microsoft.com/fr-fr/013c4aed-08d6-4dce-a124-ca807ca08959).  
  
 Étant donné que le concept d'espace de noms basé sur les dossiers n'existe pas dans [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)], les noms de fichiers de ressources :  
  
-   Proj1\\DossierA\\MonProj.bmp  
  
-   Proj1\\DossierB\\MonProj.bmp  
  
 produisent des noms de manifestes d'assembly Proj1.MonProj.bmp pour les deux fichiers.  
  
 **Pour corriger cette erreur**  
  
-   Pour corriger cette erreur, renommez les fichiers de ressources affectés \(*fichier1* et *fichier2*\).  
  
## Voir aussi  
 [NIB: Resource File Naming Conventions](http://msdn.microsoft.com/fr-fr/7b1a2cdf-6196-4034-8fc7-51a271842cc2)