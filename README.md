# priest_and_demon
## uml图
![uml图](uml.jpg)
## 实验主要目的：裁判类的制作
将“裁判类”与其他模块分开，目的是提升代码的模块化和条理性。裁判类一般承担规则判定和比赛结果裁定等逻辑控制功能，适合独立于其他模块，以确保结构清晰、职责明确、易于维护。

分离方法包括：

- **职责划分**：裁判类专注于规则判定，其他模块负责游戏角色、状态等功能，各司其职，便于管理。
- **文件结构**：将裁判类置于独立文件夹或文件中，使项目结构一目了然，方便快速定位代码。
- **接口与继承**：通过接口或继承方式独立裁判逻辑，增强模块间解耦，便于裁判规则的复用与扩展。
- **便于测试**：裁判类与其他模块分开有助于独立测试与优化，确保规则更新时不会影响其他模块。

这样分离裁判类，能保证代码在规模增大时依然保持简洁和可维护性。

在uml图中也可以看见就是其中的judgecontroller类也就是裁判类，这样更利于代码的维护!
## prefab制作
Prefab（预制件）是一种常见的游戏开发概念，通常用于 Unity 或类似的引擎中。它是一个可以**重复使用的游戏对象模板**，包含一组预定义的属性、组件和子对象，便于开发者在不同场景中复用相同的对象而无需重复配置。Prefab 制作可以有效提高开发效率，确保一致性。

### Prefab 制作步骤概述

1. **创建对象**：在场景中创建一个游戏对象，可以是简单的形状（如立方体、球体）或是包含多个组件的复杂对象，如角色、道具等。

2. **配置属性与组件**：根据需要，为对象添加各种组件（如渲染器、碰撞器、物理属性等），并设置好它的初始属性，如位置、颜色、动画等。

3. **转为 Prefab**：将配置好的对象拖动到项目窗口中的“Prefab”文件夹内，即可生成一个 Prefab 文件。此文件即为对象的模板，保存了对象的所有属性。

4. **使用 Prefab**：可以在场景中多次实例化此 Prefab，通过拖拽 Prefab 文件或编程方式来生成多个实例，所有实例都共享同一个模板设置。

5. **修改与更新**：当需要对 Prefab 进行调整时，可以双击 Prefab 文件进入编辑模式，对属性和组件进行修改。修改会自动应用到所有实例上，确保一致性。

### Prefab 的优点

- **复用性**：Prefab 是可复用的模板，适用于多种场景，节省开发时间。
- **一致性**：修改 Prefab 后会同步更新到所有实例，保持一致性。
- **动态生成**：可在运行时通过代码创建、销毁 Prefab 实例，实现动态化游戏内容。

通过合理使用 Prefab，开发者可以有效简化流程并确保项目的灵活性和一致性。
## 天空盒制作
可以按照以下步骤进行自定义天空盒的制作和设置：

### 1. 下载并导入天空盒资源包
- 使用 Unity 的 Asset Store 搜索 `Fantasy Skybox FREE`。
- 添加资源到账户并打开 Unity Editor 中的 Package Manager。
- 下载并导入资源包，完成后 `Fantasy Skybox FREE` 目录会出现在项目中。

### 2. 查看和理解天空盒材质

打开以下文件，了解不同类型的天空盒材质：
- **Cubemap 类型**（立方体贴图）： `Assets > Fantasy Skybox FREE > Cubemaps > Classic > FS000_Day_01.mat`
  - **Shader 名称**：`Skybox/Cubemap`
  - **参数**：Cubemap 是一张全景的圆形图片，Inspector 面板会显示圆形的 Cubemap 图片。
  
- **6 面贴图类型**：`Assets > Fantasy Skybox FREE > Cubemaps > FS002 > FS002_Day_Cubemap.mat`
  - **Shader 名称**：`Mobile/Skybox`
  - **参数**：包含 6 张贴图，每张代表一个面的图片。
  
- **Panoramic 类型**：`Assets > Fantasy Skybox FREE > Panoramics > FS002 > FS002_Day.mat`
  - **Shader 名称**：`Skybox/Panoramic`
  - **参数**：此类型材质使用一张全景图（Spherical）作为背景。

### 3. 自定义天空盒材质

1. 在 `Assets` 目录中右键选择 **Create > Material** 创建一个新的材质，并命名为 `mysky`。
2. 在 **Inspector** 中设置 `Shader` 为 `Skybox` 类型的三种之一，例如 `Skybox/6 Sided`。
3. 根据 `Shader` 类型，将合适的图片拖入 `Inspector` 中的参数栏：

   - **Cubemap 类型**：将 Cubemap 图片拖入 `Cubemap` 参数。
   - **6 面贴图类型**：分别将六个方向的图片（正面、背面、左侧、右侧、顶部、底部）拖入对应位置。
   - **Panoramic 类型**：将全景图拖入 `Spherical` 参数。

4. 在 `Inspector` 中调整材质的亮度、颜色、对比度等渲染配置，使天空盒与场景效果契合。

### 4. 应用天空盒材质到场景

- 打开 Unity 的 **Lighting** 设置（Window > Rendering > Lighting）窗口。
- 在 `Environment` 选项中，将 `mysky` 材质拖到 `Skybox Material` 中。
  
这样，天空盒就成功应用到场景中并生效了。

## code



