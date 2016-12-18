---
title: "Mod&#232;le Automation | Microsoft Docs"
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
  - "automation [Kit SDK Visual Studio], modèle automation"
ms.assetid: 48ddc192-96ff-46dc-a1fe-df4eb5c62c84
caps.latest.revision: 16
caps.handback.revision: 16
manager: "douge"
---
# Mod&#232;le Automation
Le modèle Automation fournit une alternative aux VSPackages pour l’extension de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]. Connu dans les versions antérieures de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] sous le nom de modèle d’extensibilité, le modèle Automation est une interface de programmation qui vous donne accès aux routines sous\-jacentes qui pilotent l’environnement de développement intégré \(IDE\), et vous permet de le personnaliser, de l’ajuster et de l’automatiser.  
  
## VSPackages et Automation  
 La documentation du Kit de développement logiciel SDK [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] est axée sur les VSPackages, qui offrent davantage de potentiel de développement que le modèle Automation. Vous pouvez par exemple écrire du code pour les objets du modèle Automation pour personnaliser un langage tel que [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)]. En revanche, vous ne pouvez pas ajouter de nouveau langage à l’IDE à l’aide du modèle Automation. Pour ajouter un nouveau langage à l’environnement, vous devez développer un VSPackage.  
  
 Ensemble, le modèle Automation et le modèle VSPackage composent une approche à deux niveaux de l’extensibilité dans [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]. L’extensibilité est la capacité à améliorer et à étendre les fonctionnalités de l’IDE. Le terme Automation fait référence au code et aux outils{b\> \<b}créés par l’utilisateur qui automatisent des tâches dans l’environnement existant et pilotent l’IDE par programmation. Les VSPackages, quant à eux, permettent d’ajouter de nouvelles fonctionnalités à l’IDE. Un VSPackage est un objet qui peut être créé conjointement ; autrement dit, il a une fabrique de classe et se rend accessible dans l’IDE en implémentant l’interface <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>.  
  
 Les compléments et les Assistants utilisent le modèle Automation pour contrôler ou étendre les fonctionnalités de l’IDE à l’aide de ses interfaces Automation. En général, Microsoft fournit de nombreux compléments avec [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]. Vous pouvez utiliser des compléments pour intégrer de nouvelles commandes aux barres d’outils et aux menus, pour ajouter des fenêtres Outil ou pour automatiser certaines tâches que vous effectuez régulièrement dans [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
 En tant que développeur de VSPackage, vous devez contribuer au modèle Automation. Par exemple, si vous ajoutez un nouveau langage à [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] à l’aide du Kit de développement logiciel SDK [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], votre langage doit fournir un modèle de code robuste qui étend le modèle existant. Pour plus d'informations, consultez [Qui contribuent au modèle Automation](../Topic/Contributing%20to%20the%20Automation%20Model.md).  
  
## Voir aussi  
 [Packages VS](../Topic/VSPackages.md)   
 [Qui contribuent au modèle Automation](../Topic/Contributing%20to%20the%20Automation%20Model.md)