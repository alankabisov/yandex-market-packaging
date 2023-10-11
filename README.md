# Packaging algorithm for Yandex.Market Hackathon

There is a Yandex.Market warehouse where orders are processed, packed, and sent for delivery. Packers (“users”) take prepared goods from a list and pack them into suitable packaging - cardboard boxes, film, or bags.
Task: to select the optimal packaging for each set of goods, so that the items can fit inside and the size of the box is not too large.
Currently, there is a heuristic algorithm that selects packaging based on the total volume of all items in the order and their sizes. However, users often reject its suggestions and pack the goods in a different box or packaging.
We need to find a way to improve this algorithm.

**Slutions:**
- Creating model only for orders with less than or equal to 3 orders (95% of dataset) and using separate column for each dimension. This way we can convert the data to "1 sample - 1 target" type and solve it with supervised ML algorithms.
- Use [Multi Instance Learning](https://nilg.ai/202105/an-introduction-to-multiple-instance-learning/) technique which allows to solve our task as classical supervised machine learning problem.