---
title: "Pointeurs intelligents (Modern C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 909ef870-904c-49b6-b8cd-e9d0b7dc9435
caps.latest.revision: 26
caps.handback.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Pointeurs intelligents (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans la programmation C\+\+ moderne, la bibliothèque standard inclut des *pointeurs intelligents*, utilisés pour garantir que les programmes sont exempts de fuites de mémoire et de ressources et qu'ils sont sécurisés du point de vue des exceptions.  
  
## Utilisations pour les pointeurs intelligents  
 Les pointeurs intelligents sont définis dans l'espace de noms `std` du fichier d'en\-tête [\<mémoire\>](../standard-library/memory.md).  Ils sont essentiels à l'idiome de programmation [RAII](../cpp/objects-own-resources-raii.md) ou *Resource Acquisition Is Initialialization*.  L'objectif principal de cet idiome est de garantir que l'acquisition des ressources se produit en même temps que l'initialisation de l'objet, afin que toutes les ressources de l'objet soient créées et préparées en une seule ligne de code.  En pratique, le grand principe de RAII est de donner la propriété de toute ressource allouée par tas, par exemple la mémoire allouée dynamiquement ou les handles d'objet système, à un objet alloué par la pile dont le destructeur contient le code de suppression ou de libération de la ressource ainsi que le code de nettoyage associé.  
  
 Dans la plupart des cas, lorsque vous initialisez un pointeur brut ou un handle de ressource pour pointer vers une ressource réelle, passez immédiatement le pointeur à un pointeur intelligent.  En C\+\+ moderne, les pointeurs bruts sont utilisés uniquement dans les petits blocs de code à portée limitée, les boucles ou les fonctions d'assistance lorsque les performances sont essentielles et qu'il n'existe aucune chance de confusion en matière de propriété.  
  
 L'exemple suivant compare une déclaration de pointeur brut à une déclaration de pointeur intelligent.  
  
 [!code-cpp[smart_pointers_intro#1](../cpp/codesnippet/CPP/smart-pointers-modern-cpp_1.cpp)]  
  
 Comme indiqué dans l'exemple, un pointeur intelligent est un modèle de classe que vous déclarez dans la pile et que vous initialisez en utilisant un pointeur brut qui pointe vers un objet alloué par tas.  Une fois le pointeur intelligent initialisé, il possède le pointeur brut.  Cela signifie que le pointeur intelligent est chargé de supprimer la mémoire que le pointeur brut spécifie.  Le destructeur du pointeur intelligent contient l'appel à supprimer, et comme le pointeur intelligent est déclaré sur la pile, son destructeur est appelé lorsque le pointeur intelligent sort de son étendue, même si une exception est levée à un emplacement situé plus haut dans la pile.  
  
 Accédez au pointeur encapsulé en utilisant des opérateurs de pointeur familiers, `->` et `*`, que la classe de pointeur intelligent surcharge pour retourner un pointeur brut encapsulé.  
  
 L'idiome de pointeur intelligent C\+\+ ressemble à la création d'objets dans les langages tels que C\# : vous créez l'objet, puis vous laissez au système le soin de le supprimer au moment approprié.  La différence vient du fait qu'aucun récupérateur de mémoire distinct ne s'exécute en arrière\-plan ; la mémoire est gérée via les règles de portée C\+\+ standard afin que l'environnement d'exécution soit plus rapide et plus efficace.  
  
> [!IMPORTANT]
>  Veillez à toujours créer les pointeurs intelligents sur une ligne distincte de code et jamais dans une liste de paramètres, afin qu'une fuite de ressource subtile ne se produise pas suite à certaines règles d'allocation de liste de paramètres.  
  
 L'exemple suivant montre comment un type pointeur intelligent `unique_ptr` de la bibliothèque STL \(Standard Template Library\) peut être utilisé pour encapsuler un pointeur vers un objet volumineux.  
  
 [!code-cpp[smart_pointers_intro#2](../cpp/codesnippet/CPP/smart-pointers-modern-cpp_2.cpp)]  
  
 L'exemple illustre les étapes essentielles suivantes pour utiliser les pointeurs intelligents.  
  
1.  Déclarez le pointeur intelligent comme variable automatique \(locale\). \(N'utilisez pas l'expression `new` ou `malloc` sur le pointeur intelligent lui\-même.\)  
  
2.  Dans le paramètre de type, spécifiez le type pointé du pointeur encapsulé.  
  
3.  Passez un pointeur brut à un objet `new` dans le constructeur de pointeur intelligent. \(Certaines fonctions utilitaires ou certains constructeurs de pointeur intelligent le font à votre place.\)  
  
4.  Utilisez les opérateurs `->` et `*` surchargés pour accéder à l'objet.  
  
5.  Laissez le pointeur intelligent supprimer l'objet.  
  
 Les pointeurs intelligents sont conçus pour être aussi efficaces que possible, aussi bien en termes de mémoire que de performances.  Par exemple, la seule donnée membre dans `unique_ptr` est le pointeur encapsulé.  Cela signifie que `unique_ptr` a exactement la même taille que ce pointeur, soit quatre octets ou huit octets.  Accéder au pointeur encapsulé en utilisant les opérateurs de pointeur intelligent surchargé \* et \-\> n'est pas beaucoup plus lent que d'accéder directement aux pointeurs bruts.  
  
 Les pointeurs intelligents ont leurs propres fonctions membres, accessibles à l'aide de la notation par « point ».  Par exemple, certains pointeurs intelligents STL ont une fonction membre de réinitialisation qui libère la propriété du pointeur.  C'est utile lorsque vous souhaitez libérer la mémoire possédée par le pointeur intelligent avant que celui\-ci ne passe hors de portée, comme illustré dans l'exemple suivant.  
  
 [!code-cpp[smart_pointers_intro#3](../cpp/codesnippet/CPP/smart-pointers-modern-cpp_3.cpp)]  
  
 Les pointeurs intelligents permettent généralement d'accéder directement à leur pointeur brut.  Les pointeurs intelligents STL ont une fonction membre `get` à cet effet, et `CComPtr` a un membre de classe publique `p`.  En assurant l'accès direct au pointeur sous\-jacent, vous pouvez utiliser le pointeur intelligent pour gérer la mémoire dans votre propre code et continuer à passer le pointeur brut au code qui ne prend pas en charge les pointeurs intelligents.  
  
 [!code-cpp[smart_pointers_intro#4](../cpp/codesnippet/CPP/smart-pointers-modern-cpp_4.cpp)]  
  
## Genres de pointeurs intelligents  
 La section suivante résume les différents genres de pointeurs intelligents disponibles dans l'environnement de programmation Windows, et indique quand les utiliser.  
  
 **Pointeurs intelligents de bibliothèque standard C\+\+**  
 Utilisez ces pointeurs intelligents comme premier choix pour encapsuler les pointeurs vers les objets C\+\+ anciens ordinaires \(POCO\).  
  
-   `unique_ptr`    
    Autorise exactement un propriétaire du pointeur sous\-jacent.  À utiliser comme option par défaut pour POCO à moins que vous ne soyez certain d'avoir besoin de `shared_ptr`.  Peut être déplacé vers un nouveau propriétaire, mais pas copié ou partagé.  Remplace `auto_ptr`, qui est déconseillé.  Comparez à `boost::scoped_ptr`.  `unique_ptr` est petit et efficace ; la taille est un pointeur et prend en charge les références rvalue pour une insertion et une récupération rapides à partir des collections STL.  Fichier d'en\-tête : `<memory>`.  Pour plus d'informations, consultez [Comment : créer et utiliser des instances unique\_ptr](../cpp/how-to-create-and-use-unique-ptr-instances.md) et [unique\_ptr, classe](../standard-library/unique-ptr-class.md).  
  
-   `shared_ptr`    
    Pointeur intelligent de références comptabilisées.  À utiliser lorsque vous souhaitez affecter un pointeur brut à plusieurs propriétaires, par exemple, lorsque vous retournez la copie d'un pointeur à partir d'un conteneur, mais que vous souhaitez conserver l'original.  Le pointeur brut n'est pas supprimé tant que tous les propriétaires `shared_ptr` ne sont pas hors de portée ou n'ont pas abandonné la propriété.  La taille contient deux pointeurs ; un pour l'objet et un pour le bloc de contrôle partagé qui contient le nombre de références.  Fichier d'en\-tête : `<memory>`.  Pour plus d'informations, consultez [Comment : créer et utiliser des instances shared\_ptr](../cpp/how-to-create-and-use-shared-ptr-instances.md) et [shared\_ptr, classe](../standard-library/shared-ptr-class.md).  
  
-   `weak_ptr`    
    Pointeur intelligent spécifique à utiliser en collaboration avec `shared_ptr`.  `weak_ptr` fournit l'accès à un objet appartenant à une ou plusieurs instances `shared_ptr`, mais ne participe pas au décompte de références.  À utiliser lorsque vous souhaitez observer un objet, mais n'avez pas besoin qu'il demeure actif.  Obligatoire dans certains cas pour interrompre les références circulaires entre les instances `shared_ptr`.  Fichier d'en\-tête : `<memory>`.  Pour plus d'informations, consultez [Comment : créer et utiliser des instances weak\_ptr](../cpp/how-to-create-and-use-weak-ptr-instances.md) et [weak\_ptr, classe](../standard-library/weak-ptr-class.md).  
  
 **Pointeurs intelligents pour les objets COM \(programmation Windows classique\)**  
 Lorsque vous travaillez avec les objets COM, encapsulez les pointeurs d'interface dans un type de pointeur intelligent approprié.  La bibliothèque ATL \(Active Template Library\) définit plusieurs pointeurs intelligents pour différents besoins.  Vous pouvez également utiliser le type pointeur intelligent `_com_ptr_t`, que le compilateur utilise lorsqu'il crée des classes wrapper à partir de fichiers .tlb.  C'est le meilleur choix lorsque vous ne souhaitez pas inclure les fichiers d'en\-tête ATL.  
  
 [CComPtr Class](../atl/reference/ccomptr-class.md)  
 Procédez ainsi à moins que vous ne puissiez pas utiliser ATL.  Effectue un décompte des références à l'aide des méthodes `AddRef` et `Release`.  Pour plus d'informations, consultez [Comment : créer et utiliser des instances CComPtr et CComQIPtr](../cpp/how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md).  
  
 [CComQIPtr Class](../atl/reference/ccomqiptr-class.md)  
 Ressemble à `CComPtr`, mais fournit également une syntaxe simplifiée pour appeler `QueryInterface` sur les objets COM.  Pour plus d'informations, consultez [Comment : créer et utiliser des instances CComPtr et CComQIPtr](../cpp/how-to-create-and-use-ccomptr-and-ccomqiptr-instances.md).  
  
 [CComHeapPtr Class](../atl/reference/ccomheapptr-class.md)  
 Pointeur intelligent vers des objets qui utilisent `CoTaskMemFree` pour libérer de la mémoire.  
  
 [CComGITPtr Class](../atl/reference/ccomgitptr-class.md)  
 Pointeur intelligent pour les interfaces obtenues à partir de la table GIT \(Global Interface Table\).  
  
 [\_com\_ptr\_t, classe](../cpp/com-ptr-t-class.md)  
 Ressemble à `CComQIPtr` en termes de fonctionnalités mais ne dépend pas d'en\-têtes ATL.  
  
 **Pointeurs intelligents ATL pour objets POCO**  
 En plus des pointeurs intelligents pour objets COM, ATL définit également des pointeurs intelligents et des collections de pointeurs intelligents pour les objets POD \(Plain Old Data\) de C\+\+.  Dans la programmation Windows classique, ces types sont des alternatives utiles aux collections STL, surtout lorsque la portabilité du code n'est pas obligatoire ou que vous ne souhaitez pas combiner les modèles de programmation STL et ATL.  
  
 [CAutoPtr Class](../atl/reference/cautoptr-class.md)  
 Pointeur intelligent qui applique une propriété unique en transférant la propriété lors de la copie.  Comparable à la classe `std::auto_ptr` déconseillée.  
  
 [CHeapPtr Class](../atl/reference/cheapptr-class.md)  
 Pointeur intelligent pour les objets alloués à l'aide de la fonction C [malloc](../c-runtime-library/reference/malloc.md).  
  
 [CAutoVectorPtr Class](../atl/reference/cautovectorptr-class.md)  
 Pointeur intelligent pour les tableaux alloués à l'aide de `new[]`.  
  
 [CAutoPtrArray Class](../atl/reference/cautoptrarray-class.md)  
 Classe qui encapsule un tableau d'éléments `CAutoPtr`.  
  
 [CAutoPtrList Class](../atl/reference/cautoptrlist-class.md)  
 Classe qui encapsule les méthodes de manipulation d'une liste de nœuds `CAutoPtr`.  
  
## Voir aussi  
 [Bienvenue dans C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)   
 [Bibliothèque standard C\+\+](../standard-library/cpp-standard-library-reference.md)   
 [\(NOTINBUILD\)Overview: Memory Management in C\+\+](http://msdn.microsoft.com/fr-fr/2201885d-3d91-4a6e-aaa6-7a554e0362a8)