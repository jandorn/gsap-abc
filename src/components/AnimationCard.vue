<script setup lang="ts">
import { Card, CardContent, CardDescription, CardFooter, CardHeader, CardTitle } from '@/components/ui/card'
import { Tabs, TabsContent, TabsList, TabsTrigger } from '@/components/ui/tabs'
import { Badge } from '@/components/ui/badge'
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
    <TabsContent value="animation">
      <Card>
        <CardHeader>
          <CardTitle>
            Animation Title 
            <a href="https://gsap.com/docs/v3/Plugins/ScrollTrigger/" target="_blank">
              <Badge class="ml-4 rounded-full" variant="outline">ScrollTrigger</Badge>
            </a>
          </CardTitle>
        </CardHeader>
        <CardContent class="space-y-2">
          Content
        </CardContent>
        <!-- <CardFooter>
          Footer
        </CardFooter> -->
      </Card>
    </TabsContent>
    <TabsContent value="code">
      <Card class="bg-[#394D3F] text-[#cfd1d5]">
        <CardContent class="m-4 p-0 font-mono text-sm font-light">
          Code
        </CardContent>
      </Card>
    </TabsContent>
  </Tabs>
</template>
