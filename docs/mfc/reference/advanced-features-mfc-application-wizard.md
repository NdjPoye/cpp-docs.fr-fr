---
title: "Fonctionnalités avancées, Assistant Application MFC | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.mfc.exe.advanced
dev_langs:
- C++
helpviewer_keywords:
- MFC Application Wizard, advanced features
ms.assetid: 8a6681c5-6576-4b12-841a-6862beee76fa
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ab9e67efc6fad90f2f9eb140411d063320f09feb
ms.lasthandoff: 02/24/2017

---
# <a name="advanced-features-mfc-application-wizard"></a>Fonctionnalités avancées, Assistant Application MFC
La rubrique répertorie les options de fonctionnalités supplémentaires de l’application, telles que l’aide, la prise en charge de l’impression, etc. Dans chaque section, spécifiez la prise en charge supplémentaire de ces fonctionnalités avancées.  
  
 **Aide contextuelle (HTML)**  
 Génère un ensemble de fichiers d’aide pour l’aide contextuelle, accessible via la touche F1 de menu ou en cliquant sur un **aide** bouton dans une boîte de dialogue. La prise en charge de l'aide nécessite le compilateur d'aide. Si vous n'en disposez pas, vous pouvez l'installer en exécutant à nouveau le programme d'installation.  
  
 Consultez la page [HTML Help : aide contextuelle pour vos programmes](../../mfc/html-help-context-sensitive-help-for-your-programs.md) et [fichiers d’aide (HTML Help)](../../ide/help-files-html-help.md) pour plus d’informations.  
  
 **Impression et Aperçu avant impression**  
 Génère du code pour gérer l’impression, imprimer le programme d’installation et les commandes de l’aperçu avant impression en appelant les fonctions membres la [CView (classe)](../../mfc/reference/cview-class.md) à partir de la bibliothèque MFC. L'Assistant ajoute également des commandes pour ces fonctions au menu de l'application. Prise en charge de l’impression est disponible uniquement pour les applications qui spécifient **prise en charge d’architecture Document/vue** dans les [Type d’Application, Assistant Application MFC](../../mfc/reference/application-type-mfc-application-wizard.md) page de l’Assistant. Par défaut, les applications à architecture Document/Vue disposent d'une prise en charge de l'impression.  
  
 **Automation**  
 Spécifie que l'application peut manipuler des objets implémentés dans une autre application ou expose l'application aux clients Automation.  
  
 **Contrôles ActiveX**  
 Prend en charge les contrôles ActiveX (valeur par défaut). Si vous ne pas sélectionner cette option et que vous souhaitez ultérieurement insérer des contrôles ActiveX dans votre projet, vous devez ajouter un appel à [AfxEnableControlContainer](http://msdn.microsoft.com/library/7aa0b9d2-5329-4bc3-9d41-856e30fe2c2b) dans votre application [CWinApp::InitInstance](../../mfc/reference/cwinapp-class.md#initinstance) fonction membre.  
  
 **MAPI (API de messagerie)**  
 Spécifie que l'application peut créer, manipuler, transférer et stocker des messages électroniques.  
  
 **Sockets Windows**  
 Prend en charge Windows Sockets, que vous pouvez utiliser pour écrire des applications qui communiquent sur les réseaux TCP/IP.  
  
 **Active Accessibility**  
 Ajoute la prise en charge de [IAccessible](http://msdn.microsoft.com/library/windows/desktop/dd318466) à [CWnd](../../mfc/reference/cwnd-class.md)-les classes dérivées, qui vous permet de personnaliser l’interface utilisateur pour une meilleure interaction avec les clients d’accessibilité.  
  
 **Manifeste des contrôles communs**  
 Activé par défaut. Génère un manifeste d'application qui active la DLL de contrôles communs incluse dans Microsoft Windows XP et des systèmes d'exploitation plus récents.  
  
 La version 6 de la DLL de contrôles communs ne met pas automatiquement à jour la version précédente des contrôles communs utilisée par vos applications existantes. Pour utiliser la version 6 de la DLL de contrôles communs, vous devez créer un manifeste d'application qui commande à votre application de charger la DLL. Cette DLL de contrôles communs prend également en charge les thèmes Windows XP.  
  
 Un manifeste d'application peut également spécifier d'autres DLL et versions demandées par votre application. Pour plus d’informations sur les manifestes d’application, consultez la page [Applications isolées et assemblys côte à côte](http://msdn.microsoft.com/library/dd408052) dans les [!INCLUDE[winsdkshort](../../atl-mfc-shared/reference/includes/winsdkshort_md.md)].  
  
 **Prise en charge du Gestionnaire de redémarrage**  
 Ajoute la prise en charge de la [Gestionnaire de redémarrage Windows](http://msdn.microsoft.com/library/windows/desktop/aa373680\(v=vs.85\).aspx). Cette vidéo montre comment utiliser le Gestionnaire de redémarrage à partir de MFC : [comment faire pour utiliser le nouveau Restart Manager](http://msdn.microsoft.com/vstudio/ee886407).  
  
 **Volets de frames avancés**  
 |Option|Description|  
|------------|-----------------|  
|**Volet d’ancrage Explorateur**|Crée un volet d’ancrage qui ressemble à Visual Studio **l’Explorateur de solutions** à gauche de la fenêtre frame principale.|  
|**Trame d’ancrage sortie**|Crée un volet d’ancrage qui ressemble à Visual Studio **sortie** volet se trouve sous la fenêtre frame principale.|  
|**Volet d’ancrage propriétés**|Crée un volet d’ancrage qui ressemble à Visual Studio **propriétés** volet à droite de la fenêtre frame principale.|  
|**Volet de navigation**|Crée un volet d'ancrage qui ressemble à la barre de navigation Outlook et se trouve à gauche de la fenêtre frame principale.|  
|**Barre de légende**|Crée une barre de légende de style Office au-dessus de la fenêtre frame principale.|  
  
 **Nombre de fichiers dans la liste des fichiers récents**  
 Spécifie le nombre de fichiers à répertorier dans la liste des derniers fichiers utilisés. Le nombre par défaut est 4.  
  
## <a name="see-also"></a>Voir aussi  
 [Assistant Application MFC](../../mfc/reference/mfc-application-wizard.md)


