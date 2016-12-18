---
title: "Cr&#233;ation de pages d’options &#224; l’aide des assemblys d’interop&#233;rabilit&#233; | Microsoft Docs"
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
  - "pages Outils Options [Kit de développement logiciel (SDK) Visual Studio], création à l’aide des assemblys d’interopérabilité"
  - "assemblys d’interopérabilité, création de pages Outils Options"
ms.assetid: 7a03f2f5-a53e-4a46-877f-5b10dd82dbc3
caps.latest.revision: 30
caps.handback.revision: 30
manager: "douge"
---
# Cr&#233;ation de pages d’options &#224; l’aide des assemblys d’interop&#233;rabilit&#233;
Les VSPackages managés peuvent utiliser les assemblys d’interopérabilité COM du [!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)] pour étendre l’environnement de développement intégré \(IDE\) de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], en ajoutant des pages **Options** au menu **Outils**.  
  
 Une page **Outils Options** est fondamentalement un contrôle utilisateur et est codée de la même façon que n’importe quel autre contrôle utilisateur. En général, vous utilisez l’un des concepteurs de l’IDE de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] pour créer l’objet et ajouter des contrôles utilisateur.  
  
> [!NOTE]
>  Une page **Outils Options** implémentée en tant que boîte de dialogue, à l’aide d’un DialogProc pour gérer les messages Windows, doit être une boîte de dialogue non modale et ne doit pas appeler la fonction EndDialog.  
  
 Vous devez utiliser l’objet Automation fourni par le VSPackage à l’environnement pour prendre en charge les propriétés que le contrôle utilisateur affiche.  
  
 Un VSPackage qui implémente une page **Outils Options** peut prendre en charge le contrôle par programmation de ses propriétés, directement ou via le modèle Automation de l’IDE. Pour plus d’informations sur la prise en charge des pages **Outils Options** avec Automation, consultez [Création de pages d’options à l’aide d’Automation](../misc/creating-options-pages-by-using-automation.md).  
  
## Rendre les pages Outils Options disponibles pour l’IDE  
 En plus d’implémenter un contrôle utilisateur, les VSPackages doivent rendre ce contrôle disponible pour l’IDE.  
  
 Pour ce faire, effectuez l’implémentation de la méthode <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage.GetPropertyPage%2A>, qui retourne une structure <xref:Microsoft.VisualStudio.Shell.Interop.VSPROPSHEETPAGE> basée sur le GUID passé.  
  
 L’IDE utilise la structure <xref:Microsoft.VisualStudio.Shell.Interop.VSPROPSHEETPAGE> pour définir les caractéristiques d’une page **Propriétés**.  
  
 Les paramètres contenus dans son membre `dwFlags` déterminent l’interprétation exacte des autres membres de <xref:Microsoft.VisualStudio.Shell.Interop.VSPROPSHEETPAGE>. La structure fournit généralement les éléments suivants :  
  
-   Un pointeur vers l’instance à partir de laquelle charger une ressource de type icône ou chaîne  
  
-   L’identificateur de ressource des modèles de boîte de dialogue de la page  
  
-   Un pointeur vers le DialogProc de la page  
  
## Inscription d’une page Outils Options  
 Vous pouvez inscrire une page **Outils Options** en créant une entrée de Registre à l’emplacement suivant : HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\*\<Version\>*\\ToolsOptionsPages, où *\<Version\>* est la version de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] \(8.0, par exemple\).  
  
 Pour inscrire la page, vous pouvez modifier manuellement le Registre ou utiliser un script de Registre \(fichier .rgs\). Pour plus d'informations, consultez [Creating Registrar Scripts](../atl/creating-registrar-scripts.md).  
  
## Voir aussi  
 [Extension de l'environnement Visual Studio](../Topic/Extending%20the%20Visual%20Studio%20Environment.md)   
 [Creating Registrar Scripts](../atl/creating-registrar-scripts.md)   
 [Prise en charge d'Automation pour les Pages d'Options](../Topic/Automation%20Support%20for%20Options%20Pages.md)   
 [Utilisation des pages d’options](../misc/using-options-pages.md)   
 [Création de Pages d'Options](../Topic/Creating%20Options%20Pages.md)   
 [Création de pages d’options à l’aide d’Automation](../misc/creating-options-pages-by-using-automation.md)