---
title: "Fonctionnalit&#233;s avanc&#233;es, Assistant Application MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.exe.advanced"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant Application MFC, fonctionnalités avancées"
ms.assetid: 8a6681c5-6576-4b12-841a-6862beee76fa
caps.latest.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 17
---
# Fonctionnalit&#233;s avanc&#233;es, Assistant Application MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La rubrique répertorie les options de fonctionnalités supplémentaires de l'application, telles que l'aide, la prise en charge de l'impression, etc.  Dans chaque section, spécifiez la prise en charge supplémentaire de ces fonctionnalités avancées.  
  
 **Aide contextuelle \(HTML\)**  
 Génère un ensemble de fichiers d'aide pour proposer une aide contextuelle, accessible via la touche F1 et le menu Aide ou en cliquant sur un bouton **Aide** dans une boîte de dialogue.  La prise en charge de l'aide nécessite le compilateur d'aide.  Si vous n'en disposez pas, vous pouvez l'installer en exécutant à nouveau le programme d'installation.  
  
 Pour plus d'informations, consultez [Aide HTML : aide contextuelle pour vos programmes](../../mfc/html-help-context-sensitive-help-for-your-programs.md) et [Fichiers d'aide \(aide HTML\)](../../ide/help-files-html-help.md).  
  
 **Impression et aperçu avant impression.**  
 Génère le code permettant de gérer les commandes d'impression, de configuration de l'impression et d'aperçu avant impression en appelant les fonctions membres de la [CView Class](../../mfc/reference/cview-class.md) de la bibliothèque MFC.  L'Assistant ajoute également des commandes pour ces fonctions au menu de l'application.  La prise en charge de l'impression est disponible uniquement pour les applications qui spécifient la **prise en charge de l'architecture Document\/Vue** dans la page [Type d'application, Assistant Application MFC](../../mfc/reference/application-type-mfc-application-wizard.md) de l'Assistant.  Par défaut, les applications à architecture Document\/Vue disposent d'une prise en charge de l'impression.  
  
 **Automation**  
 Spécifie que l'application peut manipuler des objets implémentés dans une autre application ou expose l'application aux clients Automation.  
  
 **Contrôles ActiveX**  
 Prend en charge les contrôles ActiveX \(valeur par défaut\).  Si vous ne sélectionnez pas cette option et que vous voulez par la suite insérer des contrôles ActiveX dans votre projet, vous devez ajouter un appel à [AfxEnableControlContainer](../Topic/AfxEnableControlContainer.md) dans la fonction membre [CWinApp::InitInstance](../Topic/CWinApp::InitInstance.md) de votre application.  
  
 **MAPI \(Messagerie API\)**  
 Spécifie que l'application peut créer, manipuler, transférer et stocker des messages électroniques.  
  
 **Windows Sockets**  
 Prend en charge Windows Sockets, que vous pouvez utiliser pour écrire des applications qui communiquent sur les réseaux TCP\/IP.  
  
 **Active Accessibility**  
 Ajoute la prise en charge d'[IAccessible](http://msdn.microsoft.com/library/windows/desktop/dd318466) aux classes dérivées [CWnd](../../mfc/reference/cwnd-class.md), que vous pouvez utiliser pour personnaliser l'interface utilisateur en vue d'une meilleure interaction avec les clients d'accessibilité.  
  
 **Manifeste des contrôles communs**  
 Activé par défaut.  Génère un manifeste d'application qui active la DLL de contrôles communs incluse dans Microsoft Windows XP et des systèmes d'exploitation plus récents.  
  
 La version 6 de la DLL de contrôles communs ne met pas automatiquement à jour la version précédente des contrôles communs utilisée par vos applications existantes.  Pour utiliser la version 6 de la DLL de contrôles communs, vous devez créer un manifeste d'application qui commande à votre application de charger la DLL.  Cette DLL de contrôles communs prend également en charge les thèmes Windows XP.  
  
 Un manifeste d'application peut également spécifier d'autres DLL et versions demandées par votre application.  Pour plus d'informations sur les manifestes d'application, consultez [Applications isolées et assemblys côte à côte](http://msdn.microsoft.com/library/dd408052) dans [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)].  
  
 **Prise en charge du Gestionnaire de redémarrage**  
 Ajoute la prise en charge du [Gestionnaire de redémarrage Windows](http://msdn.microsoft.com/library/windows/desktop/aa373680\(v=vs.85\).aspx).  Cette vidéo montre comment utiliser le Gestionnaire de redémarrage depuis MFC : [Procédure : Utilisation du nouveau Restart Manager](http://msdn.microsoft.com/vstudio/ee886407).  
  
 **Volets de frames avancés**  
 |Option|Description|  
|------------|-----------------|  
|**Volet d'ancrage Explorateur**|Crée un volet d'ancrage qui ressemble à l'**Explorateur de solutions** de Visual Studio et se trouve à gauche de la fenêtre frame principale.|  
|**Trame d'ancrage Sortie**|Crée un volet d'ancrage qui ressemble au volet **Sortie** de Visual Studio et se trouve sous la fenêtre frame principale.|  
|**Volet d'ancrage Propriétés**|Crée un volet d'ancrage qui ressemble au volet **Propriétés** de Visual Studio et se trouve à droite de la fenêtre frame principale.|  
|**Volet Navigation**|Crée un volet d'ancrage qui ressemble à la barre de navigation Outlook et se trouve à gauche de la fenêtre frame principale.|  
|**Barre de légende**|Crée une barre de légende de style Office au\-dessus de la fenêtre frame principale.|  
  
 **Nombre de fichiers dans la liste des fichiers récents**  
 Spécifie le nombre de fichiers à répertorier dans la liste des derniers fichiers utilisés.  Le nombre par défaut est 4.  
  
## Voir aussi  
 [Assistant Application MFC](../../mfc/reference/mfc-application-wizard.md)