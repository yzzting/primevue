<template>
    <div class="doc-main">
        <div class="doc-intro">
            <h1>Badge Theming</h1>
        </div>
        <DocSections :docs="docs" />
    </div>
    <DocSectionNav :docs="docs" />
</template>

<script>
import DocApiTable from '@/components/doc/DocApiTable.vue';
import DocStyledPreset from '@/components/doc/DocStyledPreset.vue';
import { getStyleOptions, getTokenOptions } from '@/components/doc/helpers';
import TailwindDoc from './TailwindDoc.vue';

export default {
    data() {
        return {
            docs: [
                {
                    id: 'theming.styled',
                    label: 'Styled',
                    children: [
                        {
                            id: 'theming.classes.badge',
                            label: 'Badge CSS Classes',
                            description: 'List of class names used in the styled mode.',
                            component: DocApiTable,
                            data: getStyleOptions('Badge')
                        },
                        {
                            id: 'theming.classes.overlaybadge',
                            label: 'OverlayBadge CSS Classes',
                            description: 'List of class names used in the styled mode.',
                            component: DocApiTable,
                            data: getStyleOptions('OverlayBadge')
                        },
                        {
                            id: 'theming.tokens',
                            label: 'Design Tokens',
                            description: 'List of design tokens.',
                            component: DocApiTable,
                            data: getTokenOptions('Badge')
                        },
                        {
                            id: 'theming.preset',
                            label: 'Badge Preset',
                            component: DocStyledPreset,
                            data: 'badge'
                        },
                        {
                            id: 'theming.preset',
                            label: 'OverlayBadge Preset',
                            component: DocStyledPreset,
                            data: 'overlaybadge'
                        }
                    ]
                },
                {
                    id: 'theming.unstyled',
                    label: 'Unstyled',
                    description: 'Theming is implemented with the pass through properties in unstyled mode.',
                    children: [
                        {
                            id: 'theming.tailwind',
                            label: 'Tailwind',
                            component: TailwindDoc
                        }
                    ]
                }
            ]
        };
    }
};
</script>
