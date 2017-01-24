---
title: "Composants redistribuables | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "composants redistribuables"
  - "installation [Visual Studio SDK], composants redistribuables"
ms.assetid: 5072281f-3cb3-4985-bd93-c7981233bf92
caps.latest.revision: 20
caps.handback.revision: 20
manager: "douge"
---
# Composants redistribuables
[!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)] contient du code que vous pouvez distribuer aux utilisateurs en fonction de les termes du contrat de licence logiciel [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Kit de développement logiciel.  De tels composants redistribuables incluent les package Windows Installer et les modules de fusion qui feront partie du processus d'installation de votre produit, et le code source que vous compilez dans votre VSPackages.  
  
 Le tableau suivant décrit les composants redistribuables inclus dans [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] Kit de développement logiciel.  Les composants se trouvent dans *Chemin d'installation du kit de développement Visual Studio* \\VisualStudioIntegration\\Redistributables \\.  
  
|Nom du fichier|Description|  
|--------------------|-----------------|  
|VSSDKTestHost.exe|Vous pouvez installer ce fichier exécutable dans le cadre de votre installation.|  
  
## Installer des packages redistribuables  
 Les composants redistribuables qui installent le code exécutable sont fournis comme package Windows Installer \(.msi\) afin que Microsoft puisse fournir des mises à jour s'ils sont requis pour résoudre les bogues de sécurité ou d'autres bogues critiques.  
  
 Étant donné que Windows Installer permet de convertir uniquement d'installation d'un package à la fois, l'installation d'un package redistribuable requiert que vous utilisiez un programme exécutable distinct qui installe plusieurs packages séquentiellement.  Un tel programme est souvent appelé un  *programme de chaînage* ou *un programme d'amorçage*.  
  
> [!IMPORTANT]
>  *L'installation imbriquée* \(également appelée *l'installation simultanée*\) est déconseillée dans Windows Installer parce qu'un produit « imbriqué » ne peut pas être patché indépendamment.  Elle peut être corrigée uniquement par le produit qui l'a installée.  Étant donné que les packages redistribuables de [!INCLUDE[vssdk_current_long](../misc/includes/vssdk_current_long_md.md)] installation des fichiers dans les répertoires partagés et doivent prendre en charge la mise à jour corrective indépendante, ils ne doivent pas être installés à l'aide d'une installation imbriquée.  
  
## Voir aussi  
 [Publication d’un produit](../misc/releasing-a-visual-studio-integration-product.md)