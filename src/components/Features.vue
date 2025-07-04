<script setup lang="ts">
import { Card, CardContent, CardHeader, CardTitle } from "@/components/ui/card";

import {
  Paintbrush,
  MessageCircle,
  TabletSmartphone,
  BadgeCheck,
  Goal,
  PictureInPicture,
  MousePointerClick,
  Newspaper,
} from "lucide-vue-next";

interface FeaturesProps {
  icon: string;
  title: string;
  description: string;
}

const featureList: FeaturesProps[] = [
  {
    icon: "tabletSmartphone",
    title: "移动端友好",
    description:
      "完全响应式设计，确保在所有设备上都能完美展示",
  },
  {
    icon: "badgeCheck",
    title: "社会认可",
    description:
      "与专业结构合作，曾强品牌可信度",
  },
  {
    icon: "goal",
    title: "算法可解释",
    description:
      "高度解释性算法为测试与分析提供科学且充分的依据",
  },
  {
    icon: "pictureInPicture",
    title: "强大的视觉效果",
    description:
      "丰富的图表报告提供最直观的结果，提升用户体验",
  },
  {
    icon: "mousePointerClick",
    title: "前沿智能技术",
    description:
      "前沿算法、多模态融合赋能早筛、诊断及个性化干预",
  },
  {
    icon: "newspaper",
    title: "清晰的说明与引导",
    description:
      "简明的流程加上清晰的引导助力用户快速上手",
  },
];

const iconMap: Record<
  string,
  | typeof TabletSmartphone
  | typeof BadgeCheck
  | typeof Goal
  | typeof PictureInPicture
  | typeof Paintbrush
  | typeof MousePointerClick
  | typeof MessageCircle
  | typeof Newspaper
> = {
  tabletSmartphone: TabletSmartphone,
  badgeCheck: BadgeCheck,
  goal: Goal,
  pictureInPicture: PictureInPicture,
  paintbrush: Paintbrush,
  mousePointerClick: MousePointerClick,
  messageCircle: MessageCircle,
  newspaper: Newspaper,
};
</script>

<template>
  <section
    id="features"
    class="container py-24 sm:py-32"
  >
    <h2 class="text-lg text-primary text-center mb-2 tracking-wider">
      功能特点
    </h2>

    <h2 class="text-3xl md:text-4xl text-center font-bold mb-4">
      我们的与众不同
    </h2>

    <h3 class="md:w-1/2 mx-auto text-xl text-center text-muted-foreground mb-8 whitespace-nowrap">
      探索深挖独特的功能特点，这些创新将为智能话精神疾病诊疗提供重要参考。
    </h3>

    <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-4">
      <div
        v-for="{ icon, title, description } in featureList"
        :key="title"
      >
        <Card class="h-full bg-background border-0 shadow-none">
          <CardHeader class="flex justify-center items-center">
            <div
              class="bg-primary/20 p-2 rounded-full ring-8 ring-primary/10 mb-4"
            >
              <component
                :is="iconMap[icon]"
                class="size-6 text-primary"
              />
            </div>

            <CardTitle>
              {{ title }}
            </CardTitle>
          </CardHeader>

          <CardContent class="text-muted-foreground text-center">
            {{ description }}
          </CardContent>
        </Card>
      </div>
    </div>
  </section>
</template>

<style lang="less" scoped></style>
