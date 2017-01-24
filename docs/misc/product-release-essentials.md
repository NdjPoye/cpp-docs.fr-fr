---
title: "Notions de base de la publication de produits | Microsoft Docs"
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
  - "déploiement, notions de base"
  - "installation (SDK Visual Studio), notions de base"
ms.assetid: 28370bc8-f3a7-4c5e-9b35-8331cda14ff4
caps.latest.revision: 12
caps.handback.revision: 12
manager: "douge"
---
# Notions de base de la publication de produits
L’expérience qui découle de l’installation agréable et fiable d’un produit d’intégration [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] laisse une impression durable sur les utilisateurs. Mais comme une expérience d’installation négative marque tout autant les esprits, il est judicieux d’appliquer les bonnes pratiques en matière de développement et de test de l’installation.  
  
## Développement de packages d’installation Windows Installer  
 Windows Installer est le service d’installation et de configuration recommandé pour Windows et les produits d’intégration [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
> [!NOTE]
>  La documentation [!INCLUDE[vsipsdk](../mfc/includes/vsipsdk_md.md)] sur l’installation de produits d’intégration [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] s’appuie sur les concepts de Windows Installer, mais elle ne couvre pas Windows Installer à proprement dit. Pour obtenir des liens vers les sections pertinentes de la documentation Windows Installer, reportez\-vous au tableau ci\-dessous.  
  
 Dans le contexte de l’installation, un *composant* fait référence à un composant Windows Installer. Les composants, qui contiennent des ressources telles que des fichiers et des entrées de Registre, sont installés et supprimés en tant qu’unité.  
  
|Tâche|Pour plus d'informations, consultez|  
|-----------|-----------------------------------------|  
|En savoir plus sur Windows Installer|[Windows Installer](http://msdn.microsoft.com/library/aa372866.aspx)|  
|Déterminer la configuration requise de VSPackage|-   [Détecter la configuration système requise](../Topic/Detecting%20System%20Requirements.md)|  
|Découvrir comment inscrire un VSPackage dans un package d’installation|-   [Inscription du package VS](../Topic/VSPackage%20Registration.md)<br />-   [Commandes doivent être exécutés après l'Installation](../Topic/Commands%20That%20Must%20Be%20Run%20After%20Installation.md)|  
|Examiner un exemple de package d’installation|-   Exemple d’installation de l’intégration IronPython|  
  
## Prise en charge de produits côte à côte  
 Côte à côte, parfois abrégé *SxS* \(side\-by\-side\), fait référence à la possibilité d’avoir plusieurs versions du même produit installé et même exécuté simultanément. Pour les produits d’intégration [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], ce terme fait aussi référence au fait que [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] prend lui\-même en charge l’exécution côte à côte.  
  
|Tâche|Pour plus d'informations, consultez|  
|-----------|-----------------------------------------|  
|En savoir plus sur la prise en charge de plusieurs versions de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] dans votre produit d’intégration [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]|-   [Choix entre les packages VS partagés et version](../Topic/Choosing%20Between%20Shared%20and%20Versioned%20VSPackages.md)<br />-   [Gestion des composants](../Topic/Component%20Management.md)|  
|En savoir plus sur la prise en charge de plusieurs versions de votre produit d’intégration [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]|-   [Choix entre les packages VS partagés et version](../Topic/Choosing%20Between%20Shared%20and%20Versioned%20VSPackages.md)<br />-   [L’inscription des Extensions de nom de fichier pour les déploiements côte à côte](../Topic/Registering%20File%20Name%20Extensions%20for%20Side-By-Side%20Deployments.md)<br />-   [Détecter la configuration système requise](../Topic/Detecting%20System%20Requirements.md)<br />-   [Commandes doivent être exécutés après l'Installation](../Topic/Commands%20That%20Must%20Be%20Run%20After%20Installation.md)|  
  
## Test de votre produit d’intégration Visual Studio  
 La suite de tests d’intégration [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] \(VSIT\) est une série de tests qui permet de vérifier qu’un VSPackage s’intègre correctement à [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]. VSIT ne teste pas les fonctionnalités d’un VSPackage, mais vérifie qu’un VSPackage n’a pas d’incidence négative sur d’autres fonctionnalités de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] . Pour plus d’informations, consultez [Tests d’intégration Visual Studio](http://msdn.microsoft.com/fr-fr/8d741735-7d93-46c2-ab93-01da7a0e016d).