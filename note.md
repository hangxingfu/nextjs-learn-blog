# Next.js Learn Course

## css styling

添加公共的CSS文件

- global.css放在/ui，通常添加的公共文件用在顶级组件中，就是/app/layout.tsx。
- 如果用 tailwindcss，global.css中会引入

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

两种不同的方式设置样式: Tailwind & CSS modules

- tailwind 可以直接在tsx中写样式；css modules可以将文件隔离开，分隔管理。
- 两种方式在项目中都可以用。

如何使用 clsx 工具包有条件地添加类名。

- 用clsx库切换class名称

```tsx
<span
    className={clsx(
    'inline-flex items-center rounded-full px-2 py-1 text-xs',
    {
        'bg-gray-100 text-gray-500': status === 'pending',
        'bg-green-500 text-white': status === 'paid',
    },
    )}
>
```

## 自定义 font 优化

next/font 帮助开发者在build时将自定义字体下载来打包成静态资源一并托管，这样浏览器就不用再去额外请求资源了。
