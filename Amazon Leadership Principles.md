#### Customer Obsession
* Prioritize customers

#### Ownership
* Think long term and don't sacrifice for short term results
* Act on behalf of the entire company, not just the team

#### Invent and Simplify
* Leaders expect and require innovation and invention from their teams and ways to simplify

#### Are Right, A Lot
* Leaders are right a lot and have strong judgement and good instincts
* Seek diverse perspectives and work to disconfirm their beliefs

#### Learn and Be Curious
* Leaders are never done learning and always seek to improve themselves

#### Hire and Develop the Best
* Leaders raise the performance bar with every hire and promotion

#### Insist on the Highest Standard
* Leaders have relentlessly high standards

#### Think Big
* Leaders create and communicate a bold direction that inspires results

#### Bias for Action
* Speed matters in business
* Many decisions and actions are reversible and do not need extensive study
* Value calculated risk taking

#### Frugality
* Constraints breed resourcefulness, self sufficiency and invention

#### Earn Trust
* Listen attentively, speak candidly, and treat others respectfully
#### Dive Deep
* Leaders operate at all levels. 
* No task is beneath them

#### Have Backbone
* Challenge decisions when they disagree
* Once a decision is determined they commit wholly

#### Deliver Results
* Focus on the key inputs for the business and deliver them with the right quality and in a timely fashion

``` Java
import java.util.*;

class Point {
    int x, y;

    Point(int x, int y) {
        this.x = x;
        this.y = y;
    }

    @Override
    public String toString() {
        return "(" + x + ", " + y + ")";
    }

    @Override
    public boolean equals(Object obj) {
        if (this == obj) return true;
        if (obj == null || getClass() != obj.getClass()) return false;
        Point point = (Point) obj;
        return x == point.x && y == point.y;
    }

    @Override
    public int hashCode() {
        return Objects.hash(x, y);
    }
}

public class LinePoints {

    public static List<List<Point>> findLinesWithAtLeast3Points(Set<Point> points) {
        List<List<Point>> result = new ArrayList<>();
        List<Point> pointList = new ArrayList<>(points);

        // Map to store slopes and their corresponding points
        Map<String, Set<Point>> slopeMap = new HashMap<>();

        for (int i = 0; i < pointList.size(); i++) {
            Point p1 = pointList.get(i);
            for (int j = i + 1; j < pointList.size(); j++) {
                Point p2 = pointList.get(j);

                int dx = p2.x - p1.x;
                int dy = p2.y - p1.y;
                int gcd = gcd(dx, dy);
                dx /= gcd;
                dy /= gcd;

                // Ensure consistent slope representation
                if (dx < 0 || (dx == 0 && dy < 0)) {
                    dx = -dx;
                    dy = -dy;
                }

                String slopeKey = dx + "/" + dy + "_p" + p1.x + "," + p1.y;

                slopeMap.putIfAbsent(slopeKey, new HashSet<>());
                slopeMap.get(slopeKey).add(p1);
                slopeMap.get(slopeKey).add(p2);
            }
        }

        // Extract lines with at least 3 points
        for (Set<Point> group : slopeMap.values()) {
            if (group.size() >= 3) {
                result.add(new ArrayList<>(group));
            }
        }

        return result;
    }

    // Helper function to calculate GCD
    private static int gcd(int a, int b) {
        if (b == 0) return a;
        return gcd(b, a % b);
    }

    public static void main(String[] args) {
        // Example usage
        Set<Point> points = new HashSet<>();
        points.add(new Point(1, 1));
        points.add(new Point(2, 2));
        points.add(new Point(3, 3));
        points.add(new Point(4, 4));
        points.add(new Point(1, 2));
        points.add(new Point(2, 4));

        List<List<Point>> lines = findLinesWithAtLeast3Points(points);
        for (List<Point> line : lines) {
            System.out.print("Line: ");
            for (Point point : line) {
                System.out.print(point + " ");
            }
            System.out.println();
        }
    }
}

```