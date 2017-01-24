---
title: "Biblioth&#232;que de mod&#232;les Windows Runtime C++ (WRL) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: b915afce-553b-44a7-b8dc-0ab601758eb0
caps.latest.revision: 32
caps.handback.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Biblioth&#232;que de mod&#232;les Windows Runtime C++ (WRL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] ([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]) est une bibliothèque de modèles fournissant un moyen bas niveau pour créer et utiliser des composants de [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] .  
  
## <a name="benefits"></a>Avantages  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] vous permet d'implémenter et de consommer plus facilement des composants COM (Component Object Model). Elle fournit des techniques de gestion interne comme le décompte des références pour gérer la durée de vie des objets et tester des valeurs d' `HRESULT` afin de déterminer si une opération a réussi ou échoué. Pour utiliser correctement [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)], vous devez respecter soigneusement ces règles et techniques.  
  
 Les [!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)] ([!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)]) sont un moyen haut niveau et basé sur un langage d'utiliser des composants de [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] . [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] et [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] simplifient l'écriture de code pour le [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] en exécutant automatiquement les tâches de gestion interne à votre place.  
  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] et [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] offrent des avantages différents. Voici quelques raisons pour lesquelles vous pourriez souhaiter utiliser [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] au lieu de [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] :  
  
-   [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] ajoute peu d'abstraction sur l'interface binaire d'application (ABI) [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], vous offrant la possibilité de contrôler le code sous-jacent pour mieux créer ou utiliser les API de [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
-   [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] représente les valeurs `HRESULT` COM comme des exceptions. Si vous avez hérité d'une base de code qui utilise COM ou d'une base de code qui n'utilise pas d'exceptions, vous pourriez constater que [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] est un moyen plus naturel de travailler avec le [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] car vous n'avez pas besoin d'utiliser des exceptions.  
  
    > [!NOTE]
    >  [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] utilise des valeurs `HRESULT` et ne lève pas d'exceptions. En outre, la [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] utilise des pointeurs intelligents et le modèle RAII afin de s'assurer que les objets sont détruits correctement lorsque le code de votre application lève une exception. Pour plus d’informations sur les pointeurs intelligents et le modèle RAII, consultez [pointeurs intelligents](../cpp/smart-pointers-modern-cpp.md) et [objets propres ressources (RAII)](../cpp/objects-own-resources-raii.md).  
  
-   La finalité et la conception de [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] est inspirée par la bibliothèque Active Template Library (ATL), qui est un ensemble de classes C++ basées sur des modèles qui simplifie la programmation d'objets COM. Étant donné que [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] utilise du C++ standard pour encapsuler le [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], vous pouvez déplacer et interagir plus facilement avec de nombreux composants COM existants écrits en ATL vers le [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]. Si vous connaissez déjà ATL, vous pourriez constater que la programmation de [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] est plus facile.  
  
## <a name="getting-started"></a>Prise en main  
 Voici quelques ressources qui peuvent vous aider à utiliser [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] immédiatement.  
  
 [La bibliothèque Windows Runtime (WRL)](http://channel9.msdn.com/Events/Windows-Camp/Developing-Windows-8-Metro-style-apps-in-Cpp/The-Windows-Runtime-Library-WRL-)  
 Dans cette vidéo de Channel 9, vous découvrirez la manière dont les vues [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] vous aident à écrire des applications [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] et comment créer et utiliser des composants [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] .  
  
 [Comment : activer et utiliser un composant Windows Runtime](../windows/how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)  
 Indique comment utiliser [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] pour initialiser le [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] puis activer et utiliser un composant de [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] .  
  
 [Comment : effectuer des opérations asynchrones](../windows/how-to-complete-asynchronous-operations-using-wrl.md)  
 Indique comment utiliser [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] pour démarrer des opérations asynchrones et effectuer des actions lorsque les opérations se terminent.  
  
 [Comment : gérer des événements](../windows/how-to-handle-events-using-wrl.md)  
 Indique comment utiliser [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] pour s'abonner aux événements d'un objet [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] et les gérer.  
  
 [Procédure pas à pas : Création d’un composant Runtime de base de Windows](../windows/walkthrough-creating-a-basic-windows-runtime-component-using-wrl.md)  
 Indique comment utiliser [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] pour créer un composant [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] basique qui additionne deux nombres. Démontre également comment déclencher des événements et utiliser le composant d'une application [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] qui utilise JavaScript.  
  
 [Procédure pas à pas : Création d’une application Windows Store à l’aide de WRL et Media Foundation](../windows/walkthrough-creating-a-windows-store-app-using-wrl-and-media-foundation.md)  
 Découvrez comment créer une [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] application qui utilise [Microsoft Media Foundation](http://msdn.microsoft.com/library/windows/apps/ms694197).  
  
 [Comment : créer un composant COM classique](../windows/how-to-create-a-classic-com-component-using-wrl.md)  
 Montre comment utiliser [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] pour créer un composant COM de base et une méthode de base pour stocker et consommer le composant COM à partir d'une application de bureau.  
  
 [Comment : instancier directement les composants WRL](../windows/how-to-instantiate-wrl-components-directly.md)  
 Découvrez comment utiliser les fonctions [Microsoft::WRL::Make](../windows/make-function.md) et [Microsoft::WRL::Details::MakeAndInitialize](../windows/makeandinitialize-function.md) pour instancier un composant à partir du module qui le définit.  
  
 [Comment : utiliser winmdidl.exe et midlrt.exe pour créer les fichiers .h à partir des métadonnées de windows](../windows/use-winmdidl-and-midlrt-to-create-h-files-from-windows-metadata.md)  
 Montre comment consommer des composants Windows Runtime personnalisées à partir de WRL en créant un fichier IDL à partir des métadonnées .winmd.  
  
 [Procédure pas à pas : Connexion à l’aide de tâches et les requêtes HTTP XML](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)  
 Montre comment utiliser les interfaces [IXMLHTTPRequest2](http://msdn.microsoft.com/fr-fr/bbc11c4a-aecf-4d6d-8275-3e852e309908) et [IXMLHTTPRequest2Callback](http://msdn.microsoft.com/fr-fr/aa4b3f4c-6e28-458b-be25-6cce8865fc71) avec des tâches envoyant des requêtes HTTP GET et POST à un service Web dans une application [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] .  
  
 [Exemple optimiseur de voyage Bing Maps](http://code.msdn.microsoft.com/Bing-Maps-trip-optimizer-c4e037f7)  
 Utilise la `HttpRequest` classe qui est définie dans [procédure pas à pas : connexion à l’aide de tâches et les requêtes HTTP XML](../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md) dans le contexte d’un fichier XML [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)] application.  
  
 [Création d’un composant DLL Windows Runtime avec C++, exemples](http://code.msdn.microsoft.com/windowsapps/Creating-a-Windows-Runtime-6c399797)  
 Montre comment utiliser [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] pour créer un composant DLL in-process et le consommer à partir de C++/CX, JavaScript et C#.  
  
 [Exemple de jeu marble maze DirectX](http://code.msdn.microsoft.com/windowsapps/DirectX-Marble-Maze-Game-e4806345)  
 Illustre comment utiliser [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] pour gérer la durée de vie des composants COM tels que DirectX et Media Foundation dans le contexte d'un jeu 3D complet.  
  
 [L’envoi de notifications toast à partir des exemples d’applications de bureau](http://code.msdn.microsoft.com/windowsdesktop/Sending-toast-notifications-71e230a2)  
 Illustre comment utiliser [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] pour manipuler des notifications toast à partir d'une application de bureau.  
  
## <a name="includecppwrlshorttokencppwrlshortmdmd-compared-to-atl"></a>[!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] comparé à ATL  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] ressemble à la bibliothèque Active Template Library (ATL) car vous pouvez l'utiliser pour créer des objets COM petits et rapides. [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] et ATL partagent également des concepts tels que la définition d'objets dans des modules, l'inscription explicite d'interfaces et la création d'objets à l'aide de fabriques. Vous pourriez être à l'aise avec [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] si la bibliothèque ATL vous est familière.  
  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] prend en charge la fonctionnalité COM requise pour les applications [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]. Par conséquent, elle diffère de la bibliothèque ATL car elle omet la prise en charge directe des fonctionnalités COM telles que :  
  
-   agrégation ;  
  
-   implémentations stock ;  
  
-   interfaces doubles (`IDispatch`) ;  
  
-   interfaces d'énumérateur standard ;  
  
-   points de connexion ;  
  
-   interfaces détachables ;  
  
-   incorporation OLE ;  
  
-   contrôles ActiveX ;  
  
-   COM+.  
  
## <a name="concepts"></a>Concepts  
 [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] fournit des types représentant quelques concepts de base. Les sections suivantes décrivent ces types.  
  
### <a name="comptr"></a>ComPtr  
 [ComPtr](../windows/comptr-class.md) est un type de *pointeur intelligent* qui représente l'interface spécifiée par le paramètre de modèle. Utilisez `ComPtr` pour déclarer une variable pouvant accéder aux membres d'un objet dérivé de l'interface. `ComPtr` met à jour automatiquement un décompte de références pour le pointeur d'interface sous-jacent et libère l'interface lorsque le décompte de références atteint zéro.  
  
### <a name="runtimeclass"></a>RuntimeClass  
 [RuntimeClass](../windows/runtimeclass-class.md) représente une classe instanciée qui hérite d'un ensemble d'interfaces spécifiées. Un objet `RuntimeClass` peut fournir une combinaison de prise en charge pour une ou plusieurs interfaces COM [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] ou une référence faible à un composant.  
  
### <a name="module"></a>Module  
 [Module](../windows/module-class.md) représente une collection d'objets connexes. Un objet `Module` gère les fabriques de classe, qui créent des objets, et l'inscription, qui permet à d'autres applications d'utiliser un objet.  
  
### <a name="callback"></a>Rappel  
 La fonction [Callback](../windows/callback-function-windows-runtime-cpp-template-library.md) crée un objet dont la fonction membre est un gestionnaire d'événements (une méthode de rappel). Utilisez la fonction `Callback` pour écrire des opérations asynchrones.  
  
### <a name="eventsource"></a>EventSource  
 [EventSource](../windows/eventsource-class.md) sert à gérer des gestionnaires d'événements *délégués* . Utilisez [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] pour implémenter un délégué et utilisez `EventSource` pour ajouter, supprimer et appeler des délégués.  
  
### <a name="asyncbase"></a>AsyncBase  
 [AsyncBase](../windows/asyncbase-class.md) fournit des méthodes virtuelles qui représentent le modèle de programmation asynchrone [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] . Redéfinissez les membres de cette classe pour créer une classe personnalisée capable de démarrer, arrêter ou contrôler la progression d'une opération asynchrone.  
  
### <a name="ftmbase"></a>FtmBase  
 [FtmBase](../windows/ftmbase-class.md) représente un objet marshaler libre de threads. `FtmBase` crée un tableau global d'interface (GIT) et vous permet de gérer le marshaling et les objets proxy.  
  
### <a name="weakref"></a>WeakRef  
 [WeakRef](../windows/weakref-class.md) est un type de pointeur intelligent qui représente une *référence faible*, qui fait référence à un objet qui peut être accessible ou non. Un objet `WeakRef` peut être utilisé uniquement par le [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], et non par un COM classique.  
  
 Un objet `WeakRef` représente généralement un objet dont l'existence est contrôlée par un thread ou une application externe. Par exemple, un objet `WeakRef` peut faire référence à un objet fichier. Lorsque le fichier est ouvert, `WeakRef` est valide et le fichier référencé est accessible. En revanche, quand le fichier est fermé, `WeakRef` est incorrect et le fichier n'est pas accessible.  
  
## <a name="related-topics"></a>Rubriques connexes  
  
|||  
|-|-|  
|[Modèle de projet bibliothèque de classes](../windows/wrl-class-library-project-template.md)|Décrit comment accéder au modèle de projet WRL Class Library. Ce modèle permet de simplifier l'utilisation de Visual Studio pour créer des composants [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] .|  
|[API principales par catégorie](../windows/key-wrl-apis-by-category.md)|Met en surbrillance les types, les fonctions et les macros [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)] primaires.|  
|[Référence](../windows/wrl-reference.md)|Contient des informations de référence pour [!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)].|  
|[Référence rapide (Windows Runtime et Visual C++)](http://go.microsoft.com/fwlink/?LinkId=229180)|Décrit brièvement les fonctionnalités de [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] prenant en charge [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].|  
|[À l’aide de composants Windows Runtime en C++](http://go.microsoft.com/fwlink/?LinkId=229155)|Montre comment utiliser [!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)] pour créer un composant [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] de base.|