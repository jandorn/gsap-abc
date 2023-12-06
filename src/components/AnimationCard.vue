<script setup lang="ts">
import { Card, CardContent, CardDescription, CardFooter, CardHeader, CardTitle } from '@/components/ui/card'
import { Tabs, TabsContent, TabsList, TabsTrigger } from '@/components/ui/tabs'
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
          <CardTitle>Title Animation</CardTitle>
          <CardDescription>
            Make changes to your account here. Click save when you're done.
          </CardDescription>
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
        <CardContent class="m-4 p-0">
          Content
        </CardContent>
      </Card>
    </TabsContent>
  </Tabs>
</template>
