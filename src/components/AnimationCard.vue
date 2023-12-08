<script setup lang="ts">
import { ref, watchEffect } from 'vue';

import { Card, CardContent, CardDescription, CardFooter, CardHeader, CardTitle } from '@/components/ui/card'
import { Tabs, TabsContent, TabsList, TabsTrigger } from '@/components/ui/tabs'
import { Badge } from '@/components/ui/badge'

import hljs from 'highlight.js/lib/core';
import javascript from 'highlight.js/lib/languages/javascript';
import 'highlight.js/styles/github-dark.css';

hljs.registerLanguage('javascript', javascript);

const { animationTitle, linkText, linkUrl, code } = defineProps({
  animationTitle: {
    type: String,
    required: true
  },
  linkText: {
    type: String,
    required: true
  },
  linkUrl: {
    type: String,
    required: true
  },
  code: {
    type: String,
    required: true
  }
});

const highlightedCode = ref('');

watchEffect(() => {
  highlightedCode.value = hljs.highlight(code, { language: 'javascript' }).value;
});

</script>

<template>
  <Tabs default-value="animation" class="w-full mb-16">
    <TabsList class="grid w-48 grid-cols-2">
      <TabsTrigger value="animation">
        Animation
      </TabsTrigger>
      <TabsTrigger value="code">
        Code
      </TabsTrigger>
    </TabsList>
    <TabsContent class="overflow-hidden" value="animation">
      <Card>
        <CardHeader>
          <CardTitle>
            {{ animationTitle }} 
            <a :href="linkUrl" target="_blank">
              <Badge class="ml-4 rounded-full" variant="outline">{{ linkText }} </Badge>
            </a>
          </CardTitle>
        </CardHeader>
        <CardContent class="space-y-2">
          <slot />
        </CardContent>
      </Card>
    </TabsContent>
    <TabsContent value="code">
      <Card class="bg-[#394D3F] text-[#cfd1d5]">
        <CardContent class="m-4 p-0 font-mono text-sm font-light">
          <div v-html=highlightedCode></div>
        </CardContent>
      </Card>
    </TabsContent>
  </Tabs>
</template>
