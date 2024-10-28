<script lang="ts">
  import DrinkCard from './lib/DrinkCard.svelte';
  import { Droplet, Coffee, IceCream } from 'lucide-svelte';

  const guides = [
    {
      title: "Tea-Based Drinks (16oz)",
      icon: Droplet,
      steps: [
        "Prepare boba (1.5 spoons = 30g) in serving cup",
        "Add syrup to boba (1 pump = 10ml) to sweeten",
        "Fill cup with ice (1/3 cup)",
        "Pour prepared black tea to 70% full",
        "Add fruit puree (2 pumps = 20ml)",
        "Seal with film lid",
        "Shake vigorously 4-5 times to mix",
        "Pierce with wide straw and serve"
      ],
      notes: [
        "Tea should be at room temperature to preserve boba texture",
        "Shake vertically to ensure proper mixing",
        "Check boba freshness (max 4 hours at room temp)"
      ],
      ingredients: [
        {
          name: "Strawberry",
          ingredients: "Strawberry puree + Strawberry boba"
        },
        {
          name: "Peach",
          ingredients: "Peach puree + Honey tapioca"
        },
        {
          name: "Mango",
          ingredients: "Mango puree + Mango boba"
        },
        {
          name: "Blueberry",
          ingredients: "Blueberry puree + Cinnamon boba"
        }
      ]
    },
    {
      title: "Mojito-Based Drinks (16oz)",
      icon: Coffee,
      steps: [
        "Prepare boba (1.5 spoons = 30g) in serving cup",
        "Add syrup to boba (1 pump = 10ml) to sweeten",
        "Add fresh mint leaves (2-3 leaves)",
        "Add lime wedges (2 pieces)",
        "Add mojito syrup (2 pumps = 20ml)",
        "Add fruit puree (2 pumps = 20ml)",
        "Fill cup with ice (1/3 cup)",
        "Top with soda water to 90% full",
        "Stir gently with long spoon",
        "Add wide straw and serve"
      ],
      notes: [
        "Never shake carbonated drinks",
        "Stir gently to preserve bubbles",
        "Muddle mint leaves lightly when stirring"
      ],
      ingredients: [
        {
          name: "Strawberry",
          ingredients: "Strawberry puree + Strawberry boba"
        },
        {
          name: "Kiwi",
          ingredients: "Kiwi puree + Tapioca pearls"
        },
        {
          name: "Mango",
          ingredients: "Mango puree + Passion boba"
        }
      ]
    },
    {
      title: "Milkshake-Based Drinks (16oz)",
      icon: IceCream,
      steps: [
        "In blender, combine ice (1/4 cup) and ice cream (2 scoops = 80g)",
        "Add milk to 60% level",
        "Add sauce/puree (2 pumps = 20ml)",
        "Add espresso shot if required (30ml)",
        "Blend until smooth (3-5 seconds)",
        "Prepare boba (1.5 spoons = 30g) in serving cup",
        "Add syrup to boba (1 pump = 10ml) to sweeten",
        "Pour blended mixture over boba",
        "Add wide straw and serve"
      ],
      notes: [
        "Never blend boba - add after blending",
        "Keep blending time short to maintain thickness",
        "Serve immediately to prevent separation"
      ],
      ingredients: [
        {
          name: "Strawberry",
          ingredients: "Strawberry puree + Tapioca pearls"
        },
        {
          name: "Caramel",
          ingredients: "Caramel sauce + Coffee boba"
        },
        {
          name: "Chocolate",
          ingredients: "Chocolate sauce + Tapioca pearls"
        },
        {
          name: "Caramel Espresso",
          ingredients: "Caramel sauce + Coffee boba + Espresso shot"
        }
      ]
    }
  ];
</script>

<main class="max-w-4xl mx-auto p-6 space-y-6">
  <div class="bg-gray-100 p-4 rounded-lg mb-6">
    <h2 class="font-bold mb-2">Key Measurements:</h2>
    <ul class="text-sm space-y-1">
      <li>• Boba/Pearls: 1.5 standard spoons (30g)</li>
      <li>• Standard Pump: 10ml</li>
      <li>• Puree/Sauce: 2 pumps (20ml)</li>
      <li>• Syrup for Boba: 1 pump (10ml)</li>
      <li>• Ice Fill: 1/3 cup (tea/mojito), 1/4 cup (shakes)</li>
      <li>• Ice Cream Scoop: 40g per scoop</li>
    </ul>
  </div>

  {#each guides as guide}
    <DrinkCard {...guide} />
  {/each}

  <div class="bg-blue-50 p-4 rounded-lg">
    <h2 class="font-bold mb-2 text-blue-800">Quality Control Tips:</h2>
    <ul class="text-sm space-y-1 text-blue-700">
      <li>• Always prepare fresh boba every 4 hours</li>
      <li>• Keep prepared tea at room temperature</li>
      <li>• Clean pumps daily and calibrate measurements</li>
      <li>• Store syrups and purees in refrigerator</li>
      <li>• Use fresh ice and clean ice scoop every 2 hours</li>
      <li>• Check seals on all cups before serving</li>
    </ul>
  </div>
</main>

<style>
  :global(body) {
    background-color: #f9fafb;
  }
</style>