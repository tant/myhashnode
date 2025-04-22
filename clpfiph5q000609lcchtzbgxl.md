---
title: "Nextjs 14 và ant design"
datePublished: Sun Nov 26 2023 13:30:18 GMT+0000 (Coordinated Universal Time)
cuid: clpfiph5q000609lcchtzbgxl
slug: nextjs-14-va-ant-design
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/imgCpfIMoRw/upload/3a80316a07dd8e3b178ae2297ef5a5e3.jpeg
tags: nextjs, ant-design, nextjs-14

---

Sau khi thử thì mình thấy ant design phức tạp hơn tailwind cho nên lựa chọn hiện tại vẫn là tailwind với shadcn vẫn đang chân ái

Đầu tiên thì cứ tạo một cái project nextjs bình thường nha

```bash
npx create-next-app@latest
```

Sau đó vào thư mục dự án vừa tạo và cài đặt các package, thường thì mình sẽ vào đó gọi "code ." và bắt đầu sử dụng terminal ở trỏng luôn. Mình copy nguyên cái log ở đây để dành cho mấy người chịu khó nhìn thấy vấn đề là cssinjs bị khác nếu như không để ý. Còn anh em lười thì xuống dưới làm theo các bước luôn

```bash
tantran@xps-9350:~/code/next14$ npm install antd --save

added 65 packages, and audited 347 packages in 14s

107 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
tantran@xps-9350:~/code/next14$ npm ls @ant-design/cssinjs
next14@0.1.0 /home/tantran/code/next14
└─┬ antd@5.11.4
  └── @ant-design/cssinjs@1.17.5

tantran@xps-9350:~/code/next14$ npm install @ant-design/cssinjs --save

added 1 package, changed 1 package, and audited 348 packages in 2s

107 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
tantran@xps-9350:~/code/next14$ npm ls @ant-design/cssinjs
next14@0.1.0 /home/tantran/code/next14
├── @ant-design/cssinjs@1.18.0-alpha.5
└─┬ antd@5.11.4
  └── @ant-design/cssinjs@1.17.5

tantran@xps-9350:~/code/next14$ npm remove @ant-design/cssinjs

removed 1 package, and audited 347 packages in 1s

107 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
tantran@xps-9350:~/code/next14$ npm ls @ant-design/cssinjs
next14@0.1.0 /home/tantran/code/next14
└─┬ antd@5.11.4
  └── @ant-design/cssinjs@1.17.5

tantran@xps-9350:~/code/next14$ npm install @ant-design/cssinjs@1.17.5 --save

added 1 package, removed 1 package, and audited 347 packages in 1s

107 packages are looking for funding
  run `npm fund` for details

found 0 vulnerabilities
tantran@xps-9350:~/code/next14$ npm ls @ant-design/cssinjs
next14@0.1.0 /home/tantran/code/next14
├── @ant-design/cssinjs@1.17.5
└─┬ antd@5.11.4
  └── @ant-design/cssinjs@1.17.5 deduped
```

Đầu tiên cài antd bình thường

```bash
npm install antd --save
```

Sau đó kiểm tra version của cssinjs

```bash
npm ls @ant-design/cssinjs
next14@0.1.0 /home/tantran/code/next14
└─┬ antd@5.11.4
  └── @ant-design/cssinjs@1.17.5
```

Để ý phiên bản là 1.17.5 để lát nữa mình sẽ cài đúng phiên bản này. Cài sai thì sẽ bị tình trạng gọi là bóng ma, nói chung mình chưa bị nên không biết tả sao cứ biết đừng để bị là được

```bash
npm install @ant-design/cssinjs@1.17.5 --save
```

Sau đó cài thêm

```bash
npm install @ant-design/static-style-extract
```

Vậy coi như là đủ đồ hàng rồi. Giờ lo code

Vào next.config.ts tạo nội dung như sau

```typescript
/** @type {import('next').NextConfig} */
const nextConfig = {
    productionBrowserSourceMaps: true,
}

module.exports = nextConfig
```

Tạo thư mục theme và file index.tsx trong đó với nội dung như sau

```typescript
"use client";

import React from "react";
import { ConfigProvider } from "antd";

const withTheme = (node: JSX.Element) => (
    <>
      <ConfigProvider
        theme={{
          token: {
            colorPrimary: '#52c41a',
          },
        }}
      >
        <ConfigProvider
          theme={{
            token: {
              borderRadius: 16,
            },
          }}
        >
          {node}
        </ConfigProvider>
      </ConfigProvider>
    </>
  )

export default withTheme;
```

Tạo thư mục lib và file AntdRegistry.tsx ở trong đó với nội dung như sau

```typescript
'use client';

import React from 'react';
import { useServerInsertedHTML } from 'next/navigation';
import { StyleProvider, createCache, extractStyle } from '@ant-design/cssinjs';

export default function StyledComponentsRegistry({ children }: { children: React.ReactNode }) {
  const [cache] = React.useState(() => createCache());

  useServerInsertedHTML(() => (
    <style id="antd" dangerouslySetInnerHTML={{ __html: extractStyle(cache, true) }}></style>
  ));

  return <StyleProvider cache={cache}>{children}</StyleProvider>;
}
```

Rồi cuối cùng là trang chính page.tsx

```typescript
import {
  Button,
  Space,
  Divider,
} from 'antd';

const Home = function Home() {
  return (
    <>
      <section style={{ textAlign: 'center', marginTop: 48, marginBottom: 40, padding: 100 }}>
        <Space align='start'>
          <img
            style={{ width: 40, height: 40 }}
            src='https://gw.alipayobjects.com/zos/rmsportal/KDpgvguMpGfqaHPjicRK.svg'
            alt='Ant Design'
          />
          <h2 style={{ marginBottom: 0 }}>
            Ant Design (Without Sub Components)
          </h2>
        </Space>
        <Divider style={{ marginBottom: 60 }}>Divider</Divider>
        <Button type='primary' block href='/sub'>With Sub Components</Button>
      </section>
    </>
  );
}

export default Home;
```

Vậy là xong rồi đó. Còn nếu lười thì cứ dùng cái này cho nhanh khỏi nói nhiều [https://github.com/tant/nextjs14-antdesign](https://github.com/tant/nextjs14-antdesign)