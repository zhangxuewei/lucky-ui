# lucky-ui


使用以下方式引入，可以做到js部分的按需加载，但需要手动引入样式：

import { Alert } from 'happy-ui';
import 'happy-ui/esm/alert/style';
也可以使用以下方式引入：

import Alert from 'happy-ui/esm/alert'; // or import Alert from 'happy-ui/lib/alert';
import 'happy-ui/esm/alert/style'; // or import Alert from 'happy-ui/lib/alert';
以上引入样式文件的方式不太优雅，直接入口处引入全量样式文件又和按需加载的本意相去甚远。

使用者可以借助 babel-plugin-import 来进行辅助，减少代码编写量（还是增加了使用成本）。

import { Alert } from 'happy-ui';
⬇️

import Alert from 'happy-ui/lib/alert';
import 'happy-ui/lib/alert/style';
最重要的构建流程到此结束，可以发现 sideEffects 字段对于非 CSS in JS 组件库用处并不大，还是依赖 babel 插件达到完整的按需引入效果。