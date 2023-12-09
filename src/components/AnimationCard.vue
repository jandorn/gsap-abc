<script setup lang="ts">
import { Card, CardContent, CardDescription, CardFooter, CardHeader, CardTitle } from '@/components/ui/card'
import { Tabs, TabsContent, TabsList, TabsTrigger } from '@/components/ui/tabs'
import { Badge } from '@/components/ui/badge'

const { animationTitle, linkText, linkUrl } = defineProps({
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
  }
});

import { ref } from 'vue';

const slotKey = ref(0);

</script>

<template>
  <Tabs default-value="animation" class="w-full mb-16" @update:model-value="slotKey++, console.log(slotKey)">
    <TabsList class="grid w-48 grid-cols-2">
      <TabsTrigger value="animation">
        Animation
      </TabsTrigger>
      <TabsTrigger value="code">
        Code
      </TabsTrigger>
    </TabsList>
    <TabsContent class="overflow-hidden" value="animation" :key="slotKey">
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
          <slot name="animation" />
        </CardContent>
      </Card>
    </TabsContent>
    <TabsContent value="code">
      <Card class="bg-[#2F343F] text-[#cfd1d5]">
        <CardContent class="max-h-[25rem] overflow-scroll m-4 p-0 font-mono text-sm font-light scrollbar-hide">
          <slot name="code" />
        </CardContent>
      </Card>
    </TabsContent>
  </Tabs>
</template>

<style>
/* For Webkit-based browsers (Chrome, Safari and Opera) */
.scrollbar-hide::-webkit-scrollbar {
  display: none;
}

/* For IE, Edge and Firefox */
.scrollbar-hide {
  -ms-overflow-style: none;  /* IE and Edge */
  scrollbar-width: none;  /* Firefox */
}
</style>
