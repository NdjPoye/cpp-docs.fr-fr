---
title: "Utilisation de C++ AMP dans les applications Windows Store | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 85577298-2c28-4209-9470-eb21048615db
caps.latest.revision: 14
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation de C++ AMP dans les applications Windows Store
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\) dans votre application du [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] pour effectuer des calculs sur le GPU \(Graphics Processing Unit\) ou d'autres accélérateurs de calcul.  Toutefois, C\+\+ AMP ne fournit pas d'API pour utiliser directement les types Windows Runtime \(WinRT\), et Windows Runtime ne fournit pas de wrapper pour C\+\+ AMP.  Lorsque vous utilisez les types Windows Runtime dans votre code, y compris ceux que vous avez créés vous\-même, vous devez les convertir en types compatibles avec C\+\+AMP.  
  
## Considérations sur les performances  
 Si vous utilisez [!INCLUDE[cppwrt](../../build/reference/includes/cppwrt_md.md)] \([!INCLUDE[cppwrt_short](../../build/reference/includes/cppwrt_short_md.md)]\) pour créer votre application [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)], nous vous conseillons d'utiliser des types POD \(Plain\-Old\-Data\) avec le stockage contigu, par exemple, `std::vector` ou des tableaux de style C, pour les données qui seront utilisées avec C\+\+ AMP.  Cela peut vous aider à obtenir de meilleures performances qu'avec les types non POD ou les conteneurs Windows RT, car aucun marshaling ne doit se produire.  
  
 Dans un noyau C\+\+ AMP, pour accéder aux données stockées de cette façon, il suffit d'encapsuler le `std::vector` ou stockage de groupe dans un `concurrency::array_view` et d'utiliser ensuite l'affichage de tableau dans une boucle `concurrency::parallel_for_each` :  
  
```cpp  
// simple vector addition example  
std::vector<int> data0(1024, 1);  
std::vector<int> data1(1024, 2);  
std::vector<int> data_out(data0.size(), 0);  
  
concurrency::array_view<int, 1> av0(data0.size(), data0);  
concurrency::array_view<int, 1> av1(data1.size(), data1);  
concurrency::array_view<int, 1> av2(data_out.size(), data2);   
  
av2.discard_data();  
  
concurrency::parallel_for_each(av0.extent, [=](concurrency::index<1> idx) restrict(amp)  
{  
  av2[idx] = av0[idx] + av1[idx];  
});  
  
```  
  
## Marshaling des types Windows Runtime  
 Lorsque vous travaillez avec les API Windows Runtime, utilisez C\+\+ AMP sur les données stockées dans un conteneur Windows Runtime comme `Platform::Array<T>^` ou dans des types de données complexes tels que les classes ou les structs déclarées à l'aide du mot clé `ref` ou `value`.  Dans ces situations, vous devez effectuer un travail supplémentaire pour rendre les données disponibles pour C\+\+ AMP.  
  
### Platform::Array\<T\>^, où T est de type POD  
 Lorsque vous rencontrez un `Platform::Array<T>^` et que T est un type POD, vous pouvez accéder à son stockage sous\-jacent en utilisant simplement la fonction membre `get` :  
  
```cpp  
Platform::Array<float>^ arr; // Assume that this was returned by a Windows Runtime API  
concurrency::array_view<float, 1> av(arr->Length, &arr->get(0));  
  
```  
  
 Si T n'est pas un type POD, utilisez la technique décrite dans la section suivante pour utiliser les données avec C\+\+ AMP.  
  
### Types Windows Runtime : classes de référence et classes de valeur  
 C\+\+ AMP ne prend pas en charge les types de données complexes.  Cela inclut les types non POD et les types déclarés en utilisant le mot clé `ref` ou le mot clé `value`.  Si un type non pris en charge est utilisé dans un contexte `restrict(amp)`, une erreur de compilation est générée.  
  
 Lorsque vous rencontrez un type non pris en charge, vous pouvez copier les parties intéressantes de ses données dans un objet `concurrency::array`.  En plus de rendre les données disponibles pour être consommées par C\+\+ AMP, cette approche de copie manuelle peut également améliorer les performances en optimisant la localité des données et en garantissant que les données qui ne seront pas utilisées ne seront pas copiées dans l'accélérateur.  Vous pouvez améliorer davantage les performances en utilisant un  *tableau intermédiaire*, qui est une forme spéciale de `concurrency::array` fournissant un indicateur au runtime AMP selon lequel le tableau doit être optimisé pour un transfert fréquent entre lui\-même et d'autres tableaux de l'accélérateur spécifié.  
  
```cpp  
// pixel_color.h  
ref class pixel_color sealed  
{  
 public:   
  pixel_color(Platform::String^ color_name, int red, int green, int blue)   
  {  
    name = color_name;  
    r = red;  
    g = green;  
    b = blue;  
  }  
  
  property Platform::String^ name;   
  property int r;  
  property int g;  
..property int b;  
};  
  
// Some other file  
std::vector<pixel_color^> pixels (256);   
  
for(pixel_color ^pixel : pixels)   
{  
  pixels.push_back(ref new pixel_color("blue", 0, 0, 255));  
}  
// Create the accelerators  
auto cpuAccelerator = concurrency::accelerator(concurrency::accelerator::cpu_accelerator);  
auto devAccelerator = concurrency::accelerator(concurrency::accelerator::default_accelerator);  
  
// Create the staging arrays  
concurrency::array<float, 1> red_vec(256, cpuAccelerator.default_view, devAccelerator.default_view);  
concurrency::array<float, 1>  blue_vec(256, cpuAccelerator.default_view, devAccelerator.default_view);   
  
// Extract data from the complex array of structs into staging arrays.  
concurrency::parallel_for(0, 256, [&](int i)  
{   
  red_vec[i] = pixels[i]->r; blue_vec[i] = pixels[i]->b;  
});  
  
// Array views are still used to copy data to the accelerator  
concurrency::array_view<float, 1> av_red(red_vec);  
concurrency::array_view<float, 1> av_blue(blue_vec);  
  
// Change all pixels from blue to red.  
concurrency::parallel_for_each(av_red.extent, [=](index<1> idx) restrict(amp)  
{  
  av_red[idx] = 255;  
  av_blue[idx] = 0;  
});  
  
```  
  
## Voir aussi  
 [Créer votre première application Windows Store à l'aide de C\+\+](http://go.microsoft.com/fwlink/p/?LinkId=249073)   
 [Création de composants Windows runtime en C\+\+](http://go.microsoft.com/fwlink/p/?LinkId=249076)